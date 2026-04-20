---
title: Querying S3 Storage Lens Metrics Export with Athena
author: Sathyajith Bhat
type: post
date: 2026-03-25
url: /2026/03/25/querying-s3-storage-lens-metrics-with-athena/
summary: A walkthrough on setting up Athena to query S3 Storage Lens metrics exports, with useful queries for prefix-level storage trends and retrieval rates.
categories:
  - "Tips & How-To's"
tags:
  - aws
  - s3
  - athena
  - storage-lens
draft: true
---

### What is S3 Storage Lens?

[S3 Storage Lens](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage_lens.html) is an analytics feature that gives you organization-wide visibility into your S3 storage usage and activity. It aggregates metrics across all your buckets — storage size, object counts, request patterns — and presents them in a dashboard. You can scope it to specific accounts, regions, or buckets, and it updates daily.

Out of the box, the free tier gives you 28 usage metrics covering things like total storage bytes, object counts, and bucket-level summaries. That's enough for a general overview, but not much more.

### Storage Lens Advanced Metrics

[Storage Lens advanced metrics](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage_lens_basics_metrics_recommendations.html#storage_lens_basics_metrics_selection) is where it gets more useful. Enabling advanced metrics unlocks:

- **Activity metrics** — request counts broken down by type (GET, PUT, DELETE, HEAD, LIST), bytes downloaded/uploaded, and HTTP status code distributions (4xx, 5xx errors)
- **Detailed status codes** — individual counts for 200, 206, 400, 403, 404, 500, 503 responses
- **Prefix-level aggregation** — metrics scoped to specific S3 key prefixes, not just buckets. This is the big one if you want to understand which parts of a bucket are growing or being accessed.
- **Storage class-level breakdown** — usage split across Standard, Intelligent-Tiering, Glacier, etc.

Advanced metrics also retain data for 15 months (vs. 14 days for free metrics), which matters if you want to look at trends over time.

### Pricing

Storage Lens advanced metrics aren't free. As of this writing:

- **Advanced metrics and recommendations**: $0.20 per million objects monitored per month
- **Advanced activity metrics and detailed status codes**: additional $0.20 per million objects monitored per month
- **Prefix-level aggregation**: additional $0.20 per million objects monitored per month

So if you enable everything on a bucket with 100 million objects, you're looking at roughly $60/month for that bucket. The [pricing page](https://aws.amazon.com/s3/pricing/#S3_Storage_Lens) has the full breakdown. For large buckets, it's worth being selective about which advanced features you enable. While the costs seem quite prohibitive, for large petabyte scale buckets, Storage Lens Advanced Metrics can save you many times over. 

The metrics export itself is free — you only pay for the S3 storage of the exported Parquet files and the Athena queries you run against them.

### Querying the Exports with Athena

The Storage Lens dashboard is fine for a quick look, but when you need to dig deeper — tracking prefix-level growth over time, identifying cold data, or building reports — it falls short. The good news is that Storage Lens can export its daily metrics to an S3 bucket, and from there, you can query it with Athena.

Here's how I set this up.

### The Export

Storage Lens exports land in your destination bucket with this path structure:

```
s3://<bucket>/StorageLens/<account-id>/<config-name>/V_1/reports/dt=YYYY-MM-DD/
```

Each day gets its own Hive-style partition (`dt=2026-03-10`), and the data is stored as Parquet files. The export schema is a flat table where each row is a single metric measurement — so a single prefix might have rows for `StorageBytes`, `ObjectCount`, `BytesDownloaded`, and so on.

The full list of available metrics and the export schema is documented in the [AWS docs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage_lens_understanding_metrics_export_schema.html).

### Setting Up the Athena Table

The key columns in the export are:

- `record_type` — whether the metric is for an `ACCOUNT`, `BUCKET`, or `PREFIX`
- `record_value` — the actual account/bucket/prefix value (URL-encoded)
- `metric_name` / `metric_value` — the metric and its value
- `dt` — the report date, used as a partition key

Since the data is already partitioned by date, we can use [partition projection](https://docs.aws.amazon.com/athena/latest/ug/partition-projection.html) instead of manually managing partitions.

### A Quick Detour: What is Partition Projection?

Normally, when you have a partitioned Athena table, you need to tell the Glue catalog about each partition. Every time a new `dt=2026-03-11` folder appears, you'd either run `MSCK REPAIR TABLE` (which scans the entire S3 path to discover new partitions) or use `ALTER TABLE ADD PARTITION` to register it manually. For a table that gets a new partition every day, this gets tedious fast.

Partition projection flips this around. Instead of discovering partitions from S3, you tell Athena the _rules_ for how partitions are structured — the type (date, integer, enum), the range, and the format. Athena then calculates which partitions exist based on those rules and goes directly to the right S3 paths. No Glue catalog lookups, no `MSCK REPAIR TABLE`, and new partitions are available the moment the data lands.

For our Storage Lens table, the rules are simple: `dt` is a date, formatted as `yyyy-MM-dd`, incrementing by 1 day, starting from when the exports began. Here's the DDL:

```sql
CREATE EXTERNAL TABLE storage_lens_metrics (
  version_number      string,
  configuration_id    string,
  report_date         string,
  aws_account_number  string,
  aws_region          string,
  storage_class       string,
  record_type         string,
  record_value        string,
  bucket_name         string,
  metric_name         string,
  metric_value        bigint
)
PARTITIONED BY (dt string)
STORED AS PARQUET
LOCATION 's3://<destination-bucket>/StorageLens/<account-id>/<config-name>/V_1/reports/'
TBLPROPERTIES (
  'parquet.compression' = 'SNAPPY',
  'projection.enabled' = 'true',
  'projection.dt.type' = 'date',
  'projection.dt.format' = 'yyyy-MM-dd',
  'projection.dt.range' = '2025-12-09,NOW',
  'projection.dt.interval' = '1',
  'projection.dt.interval.unit' = 'DAYS',
  'storage.location.template' = 's3://<destination-bucket>/StorageLens/<account-id>/<config-name>/V_1/reports/dt=${dt}'
);
```

Replace the placeholder values with your actual bucket, account ID, and config name. The `projection.dt.range` start date should match when your exports began.

With partition projection, Athena resolves partitions on the fly. New dates get picked up automatically, and your `WHERE dt = ...` filters prune partitions so you only scan what you need.

### Querying Prefix-Level Retrieval Rates

Since each metric is a separate row, you'll need to pivot them. A subtlety: `StorageBytes` is a point-in-time snapshot for each day, while `BytesDownloaded` is that day's activity. If you group across multiple days without accounting for this, you'll get misleading ratios. The approach below uses a CTE to first compute proper daily metrics, then aggregates them into a single row per prefix:

```sql
WITH daily AS (
  SELECT
    bucket_name,
    record_value,
    dt,
    MAX(CASE WHEN metric_name = 'StorageBytes' THEN metric_value END) AS storage_bytes,
    COALESCE(MAX(CASE WHEN metric_name = 'BytesDownloaded' THEN metric_value END), 0) AS bytes_downloaded,
    MAX(CASE WHEN metric_name = 'GetRequests' THEN metric_value END) AS get_requests,
    MAX(CASE WHEN metric_name = 'AllRequests' THEN metric_value END) AS all_requests
  FROM storage_lens_metrics
  WHERE record_type = 'PREFIX'
    AND metric_name IN ('StorageBytes', 'BytesDownloaded', 'GetRequests', 'AllRequests')
    AND dt >= date_format(current_date - interval '7' day, '%Y-%m-%d')
  GROUP BY bucket_name, record_value, dt
)
SELECT
  bucket_name,
  url_decode(record_value) AS prefix,
  CASE
    WHEN avg(storage_bytes) >= 1099511627776 THEN concat(cast(round(avg(storage_bytes) / 1099511627776.0, 2) as varchar), ' TB')
    WHEN avg(storage_bytes) >= 1073741824 THEN concat(cast(round(avg(storage_bytes) / 1073741824.0, 2) as varchar), ' GB')
    WHEN avg(storage_bytes) >= 1048576 THEN concat(cast(round(avg(storage_bytes) / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(round(avg(storage_bytes), 0) as varchar), ' B')
  END AS avg_storage,
  CASE
    WHEN sum(bytes_downloaded) >= 1099511627776 THEN concat(cast(round(sum(bytes_downloaded) / 1099511627776.0, 2) as varchar), ' TB')
    WHEN sum(bytes_downloaded) >= 1073741824 THEN concat(cast(round(sum(bytes_downloaded) / 1073741824.0, 2) as varchar), ' GB')
    WHEN sum(bytes_downloaded) >= 1048576 THEN concat(cast(round(sum(bytes_downloaded) / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(sum(bytes_downloaded) as varchar), ' B')
  END AS total_downloaded,
  CASE
    WHEN sum(get_requests) >= 1000000 THEN concat(cast(round(sum(get_requests) / 1000000.0, 2) as varchar), 'M')
    WHEN sum(get_requests) >= 1000 THEN concat(cast(round(sum(get_requests) / 1000.0, 1) as varchar), 'K')
    ELSE cast(sum(get_requests) as varchar)
  END AS total_get_requests,
  CASE
    WHEN sum(all_requests) >= 1000000 THEN concat(cast(round(sum(all_requests) / 1000000.0, 2) as varchar), 'M')
    WHEN sum(all_requests) >= 1000 THEN concat(cast(round(sum(all_requests) / 1000.0, 1) as varchar), 'K')
    ELSE cast(sum(all_requests) as varchar)
  END AS total_all_requests,
  round(avg(bytes_downloaded * 100.0 / nullif(storage_bytes, 0)), 4) AS avg_daily_retrieval_rate_pct,
  round(sum(bytes_downloaded) * 100.0 / nullif(avg(storage_bytes), 0), 4) AS cumulative_retrieval_rate_pct
FROM daily
GROUP BY bucket_name, record_value
ORDER BY avg_daily_retrieval_rate_pct ASC;
```

A couple of things to note:

- `record_value` is URL-encoded in the export, so wrap it with `url_decode()` for readable prefix paths.
- If a prefix has no downloads on a date, the `BytesDownloaded` row may be absent entirely — the `COALESCE` in the CTE handles this.
- Two retrieval rate columns: `avg_daily_retrieval_rate_pct` averages each day's ratio individually, while `cumulative_retrieval_rate_pct` gives total downloaded over the period vs average storage.

Sorting by retrieval rate ascending surfaces prefixes with the most storage but least retrieval — good candidates for lifecycle policy changes or cheaper storage classes.

### Tracking Growth Over Time

To find the top growing prefixes over the last 30 days:

```sql
WITH latest AS (
  SELECT bucket_name, record_value AS prefix, metric_value AS current_bytes
  FROM storage_lens_metrics
  WHERE record_type = 'PREFIX'
    AND metric_name = 'StorageBytes'
    AND dt = (SELECT MAX(dt) FROM storage_lens_metrics)
),
previous AS (
  SELECT bucket_name, record_value AS prefix, metric_value AS previous_bytes
  FROM storage_lens_metrics
  WHERE record_type = 'PREFIX'
    AND metric_name = 'StorageBytes'
    AND dt = (SELECT MAX(dt) FROM storage_lens_metrics
              WHERE dt <= date_format(current_date - interval '30' day, '%Y-%m-%d'))
)
SELECT
  l.bucket_name,
  url_decode(l.prefix) AS prefix,
  CASE
    WHEN p.previous_bytes >= 1099511627776 THEN concat(cast(round(p.previous_bytes / 1099511627776.0, 2) as varchar), ' TB')
    WHEN p.previous_bytes >= 1073741824 THEN concat(cast(round(p.previous_bytes / 1073741824.0, 2) as varchar), ' GB')
    WHEN p.previous_bytes >= 1048576 THEN concat(cast(round(p.previous_bytes / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(p.previous_bytes as varchar), ' B')
  END AS previous_size,
  CASE
    WHEN l.current_bytes >= 1099511627776 THEN concat(cast(round(l.current_bytes / 1099511627776.0, 2) as varchar), ' TB')
    WHEN l.current_bytes >= 1073741824 THEN concat(cast(round(l.current_bytes / 1073741824.0, 2) as varchar), ' GB')
    WHEN l.current_bytes >= 1048576 THEN concat(cast(round(l.current_bytes / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(l.current_bytes as varchar), ' B')
  END AS current_size,
  CASE
    WHEN abs(l.current_bytes - p.previous_bytes) >= 1099511627776 THEN concat(cast(round((l.current_bytes - p.previous_bytes) / 1099511627776.0, 2) as varchar), ' TB')
    WHEN abs(l.current_bytes - p.previous_bytes) >= 1073741824 THEN concat(cast(round((l.current_bytes - p.previous_bytes) / 1073741824.0, 2) as varchar), ' GB')
    WHEN abs(l.current_bytes - p.previous_bytes) >= 1048576 THEN concat(cast(round((l.current_bytes - p.previous_bytes) / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(l.current_bytes - p.previous_bytes as varchar), ' B')
  END AS growth,
  round((l.current_bytes - p.previous_bytes) * 100.0 / nullif(p.previous_bytes, 0), 2) AS growth_pct
FROM latest l
JOIN previous p ON l.bucket_name = p.bucket_name AND l.prefix = p.prefix
ORDER BY (l.current_bytes - p.previous_bytes) DESC
LIMIT 20;
```

And for month-over-month trends:

```sql
WITH monthly AS (
  SELECT
    bucket_name,
    record_value AS prefix,
    substr(dt, 1, 7) AS month,
    avg(metric_value) AS avg_bytes
  FROM storage_lens_metrics
  WHERE record_type = 'PREFIX'
    AND metric_name = 'StorageBytes'
  GROUP BY bucket_name, record_value, substr(dt, 1, 7)
)
SELECT
  bucket_name,
  url_decode(prefix) AS prefix,
  month,
  CASE
    WHEN avg_bytes >= 1099511627776 THEN concat(cast(round(avg_bytes / 1099511627776.0, 2) as varchar), ' TB')
    WHEN avg_bytes >= 1073741824 THEN concat(cast(round(avg_bytes / 1073741824.0, 2) as varchar), ' GB')
    WHEN avg_bytes >= 1048576 THEN concat(cast(round(avg_bytes / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(round(avg_bytes, 0) as varchar), ' B')
  END AS avg_storage,
  CASE
    WHEN abs(avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) >= 1099511627776
      THEN concat(cast(round((avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) / 1099511627776.0, 2) as varchar), ' TB')
    WHEN abs(avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) >= 1073741824
      THEN concat(cast(round((avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) / 1073741824.0, 2) as varchar), ' GB')
    WHEN abs(avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) >= 1048576
      THEN concat(cast(round((avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(round(avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month), 0) as varchar), ' B')
  END AS mom_growth
FROM monthly
ORDER BY bucket_name, prefix, month;
```

### Exporting to S3 Table Buckets

Storage Lens can also export to [S3 Table Buckets](https://docs.aws.amazon.com/AmazonS3/latest/userguide/s3-tables-buckets.html) instead of general purpose buckets. Table Buckets store data as Apache Iceberg tables, which means no DDL to write, no partition projection to configure, and no `MSCK REPAIR TABLE` to run — Athena can query them directly.

The export splits into three separate tables instead of the flat metric name/value format:

- `default_storage_metrics` — storage bytes, object counts, encryption, replication, size distribution
- `default_activity_metrics` — request counts, bytes transferred, status codes, latency
- `bucket_property_metrics` — versioning, lifecycle rules, replication rules

The big advantage is that metrics are actual columns instead of name/value pairs, so queries are simpler and there's no pivoting. The tradeoff is that you need to join across tables when you want both storage and activity data together.

To query these in Athena, select the S3 Tables catalog as your data source. The catalog name follows the format `s3tablescatalog/<table-bucket-name>`, and the namespace matches your Storage Lens configuration.

Here are the equivalent queries for S3 Table Buckets:

### Retrieval Rate by Prefix (S3 Tables)

```sql
WITH daily AS (
  SELECT
    s.bucket_name,
    s.record_value AS prefix,
    s.report_time,
    s.storage_bytes,
    COALESCE(a.downloaded_bytes, 0) AS downloaded_bytes,
    a.get_request_count,
    a.all_request_count
  FROM "s3tablescatalog/<table-bucket>"."<namespace>".default_storage_metrics s
  LEFT JOIN "s3tablescatalog/<table-bucket>"."<namespace>".default_activity_metrics a
    ON s.bucket_name = a.bucket_name
    AND s.record_type = a.record_type
    AND s.record_value = a.record_value
    AND s.report_time = a.report_time
    AND s.aws_region = a.aws_region
    AND s.storage_class = a.storage_class
  WHERE s.record_type = 'PREFIX'
    AND cast(s.report_time as date) >= current_date - interval '7' day
)
SELECT
  bucket_name,
  prefix,
  CASE
    WHEN avg(storage_bytes) >= 1099511627776 THEN concat(cast(round(avg(storage_bytes) / 1099511627776.0, 2) as varchar), ' TB')
    WHEN avg(storage_bytes) >= 1073741824 THEN concat(cast(round(avg(storage_bytes) / 1073741824.0, 2) as varchar), ' GB')
    WHEN avg(storage_bytes) >= 1048576 THEN concat(cast(round(avg(storage_bytes) / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(round(avg(storage_bytes), 0) as varchar), ' B')
  END AS avg_storage,
  CASE
    WHEN sum(downloaded_bytes) >= 1099511627776 THEN concat(cast(round(sum(downloaded_bytes) / 1099511627776.0, 2) as varchar), ' TB')
    WHEN sum(downloaded_bytes) >= 1073741824 THEN concat(cast(round(sum(downloaded_bytes) / 1073741824.0, 2) as varchar), ' GB')
    WHEN sum(downloaded_bytes) >= 1048576 THEN concat(cast(round(sum(downloaded_bytes) / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(sum(downloaded_bytes) as varchar), ' B')
  END AS total_downloaded,
  CASE
    WHEN sum(get_request_count) >= 1000000 THEN concat(cast(round(sum(get_request_count) / 1000000.0, 2) as varchar), 'M')
    WHEN sum(get_request_count) >= 1000 THEN concat(cast(round(sum(get_request_count) / 1000.0, 1) as varchar), 'K')
    ELSE cast(sum(get_request_count) as varchar)
  END AS total_get_requests,
  CASE
    WHEN sum(all_request_count) >= 1000000 THEN concat(cast(round(sum(all_request_count) / 1000000.0, 2) as varchar), 'M')
    WHEN sum(all_request_count) >= 1000 THEN concat(cast(round(sum(all_request_count) / 1000.0, 1) as varchar), 'K')
    ELSE cast(sum(all_request_count) as varchar)
  END AS total_all_requests,
  round(avg(downloaded_bytes * 100.0 / nullif(storage_bytes, 0)), 4) AS avg_daily_retrieval_rate_pct,
  round(sum(downloaded_bytes) * 100.0 / nullif(avg(storage_bytes), 0), 4) AS cumulative_retrieval_rate_pct
FROM daily
GROUP BY bucket_name, prefix
ORDER BY avg_daily_retrieval_rate_pct ASC;
```

No `url_decode()` needed — `record_value` isn't URL-encoded in S3 Tables exports.

### Top Growing Prefixes (S3 Tables)

```sql
WITH latest AS (
  SELECT bucket_name, record_value AS prefix, storage_bytes AS current_bytes
  FROM "s3tablescatalog/<table-bucket>"."<namespace>".default_storage_metrics
  WHERE record_type = 'PREFIX'
    AND cast(report_time as date) = (
      SELECT MAX(cast(report_time as date))
      FROM "s3tablescatalog/<table-bucket>"."<namespace>".default_storage_metrics
    )
),
previous AS (
  SELECT bucket_name, record_value AS prefix, storage_bytes AS previous_bytes
  FROM "s3tablescatalog/<table-bucket>"."<namespace>".default_storage_metrics
  WHERE record_type = 'PREFIX'
    AND cast(report_time as date) = (
      SELECT MAX(cast(report_time as date))
      FROM "s3tablescatalog/<table-bucket>"."<namespace>".default_storage_metrics
      WHERE cast(report_time as date) <= current_date - interval '30' day
    )
)
SELECT
  l.bucket_name,
  l.prefix,
  CASE
    WHEN p.previous_bytes >= 1099511627776 THEN concat(cast(round(p.previous_bytes / 1099511627776.0, 2) as varchar), ' TB')
    WHEN p.previous_bytes >= 1073741824 THEN concat(cast(round(p.previous_bytes / 1073741824.0, 2) as varchar), ' GB')
    WHEN p.previous_bytes >= 1048576 THEN concat(cast(round(p.previous_bytes / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(p.previous_bytes as varchar), ' B')
  END AS previous_size,
  CASE
    WHEN l.current_bytes >= 1099511627776 THEN concat(cast(round(l.current_bytes / 1099511627776.0, 2) as varchar), ' TB')
    WHEN l.current_bytes >= 1073741824 THEN concat(cast(round(l.current_bytes / 1073741824.0, 2) as varchar), ' GB')
    WHEN l.current_bytes >= 1048576 THEN concat(cast(round(l.current_bytes / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(l.current_bytes as varchar), ' B')
  END AS current_size,
  CASE
    WHEN abs(l.current_bytes - p.previous_bytes) >= 1099511627776 THEN concat(cast(round((l.current_bytes - p.previous_bytes) / 1099511627776.0, 2) as varchar), ' TB')
    WHEN abs(l.current_bytes - p.previous_bytes) >= 1073741824 THEN concat(cast(round((l.current_bytes - p.previous_bytes) / 1073741824.0, 2) as varchar), ' GB')
    WHEN abs(l.current_bytes - p.previous_bytes) >= 1048576 THEN concat(cast(round((l.current_bytes - p.previous_bytes) / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(l.current_bytes - p.previous_bytes as varchar), ' B')
  END AS growth,
  round((l.current_bytes - p.previous_bytes) * 100.0 / nullif(p.previous_bytes, 0), 2) AS growth_pct
FROM latest l
JOIN previous p ON l.bucket_name = p.bucket_name AND l.prefix = p.prefix
ORDER BY (l.current_bytes - p.previous_bytes) DESC
LIMIT 20;
```

### Month-over-Month Trends (S3 Tables)

```sql
WITH monthly AS (
  SELECT
    bucket_name,
    record_value AS prefix,
    date_format(report_time, '%Y-%m') AS month,
    avg(storage_bytes) AS avg_bytes
  FROM "s3tablescatalog/<table-bucket>"."<namespace>".default_storage_metrics
  WHERE record_type = 'PREFIX'
  GROUP BY bucket_name, record_value, date_format(report_time, '%Y-%m')
)
SELECT
  bucket_name,
  prefix,
  month,
  CASE
    WHEN avg_bytes >= 1099511627776 THEN concat(cast(round(avg_bytes / 1099511627776.0, 2) as varchar), ' TB')
    WHEN avg_bytes >= 1073741824 THEN concat(cast(round(avg_bytes / 1073741824.0, 2) as varchar), ' GB')
    WHEN avg_bytes >= 1048576 THEN concat(cast(round(avg_bytes / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(round(avg_bytes, 0) as varchar), ' B')
  END AS avg_storage,
  CASE
    WHEN abs(avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) >= 1099511627776
      THEN concat(cast(round((avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) / 1099511627776.0, 2) as varchar), ' TB')
    WHEN abs(avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) >= 1073741824
      THEN concat(cast(round((avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) / 1073741824.0, 2) as varchar), ' GB')
    WHEN abs(avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) >= 1048576
      THEN concat(cast(round((avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month)) / 1048576.0, 2) as varchar), ' MB')
    ELSE concat(cast(round(avg_bytes - lag(avg_bytes) OVER (PARTITION BY bucket_name, prefix ORDER BY month), 0) as varchar), ' B')
  END AS mom_growth
FROM monthly
ORDER BY bucket_name, prefix, month;
```

### Why This Is Useful

The Storage Lens dashboard is great for a quick look, but being able to query the raw data opens up a lot more:

- Build automated reports on storage growth and cost trends
- Identify cold prefixes that haven't been accessed in weeks — candidates for lifecycle rules or Glacier transitions
- Correlate request patterns (4xx errors, GET/PUT ratios) with specific prefixes
- Track the effectiveness of lifecycle policies you've already put in place

The daily export is free (you just pay for the S3 storage of the export itself and the Athena queries), so there's little reason not to have it running.

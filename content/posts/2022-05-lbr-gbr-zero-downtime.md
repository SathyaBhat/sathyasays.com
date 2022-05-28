---
title: Migrating Route 53 records from Latency Based Routing to Geolocation routing with zero downtime
author: Sathyajith Bhat
type: post
date: 2022-05-28
url: /2022/05/28/route53-latency-geolocation-migration
description: I had some fun playing with Route 53's routing policies.
featured_image: 
meta_image: 
categories:
  - DevOps
tags:
  - Route 53
  - DNS
---

[Amazon Route 53](https://aws.amazon.com/route53/) is a pretty incredible managed Domain Name System(DNS) service. DNS translates domain names to IP addresses and allows for computers to connect to each other. More than just a managed DNS service, Route 53 lets us create records using different routing polices. The routing policy determines how Route 53 responds to a DNS request.

### Primer on Routing Policies

Route 53 supports the following routing polices. 

* Simple routing - This is a standard DNS record with no Route 53 routing. This is what most other DNS services would do.
* Failover routing - This policy lets us route traffic to an alternate resource when the primary resource is unhealthy.
* Geolocation routing ("GBR") - This policy lets us route traffic to different resources based on the geographic location of where the request is originating from.
* Latency based routing ("LBR") - This policy lets us route traffic to various resources based on the best latency that was measured.

These policies are setup when you create a Route 53 record.

### Latency-based routing

Latency-based routing ("LBR") is a nifty way of improving performance for your application. With LBR, AWS automatically and transparently routes traffic to the least-latency resource across the configured regions. AWS does this by determining which region provides the lowest latency, and routing the traffic to the region. If you're interested in the details behind how AWS does this, do read their documention on [How Amazon Route 53 uses EDNS0 to estimate the location of a user](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-edns0).

At work, a lot of the services that did not need multi-region routing were configured with simple routing. For services that could handle multi-region but had backing services and thus could not handle auto-failover would be configured with LBR without health-checks. In the case where a failover was required, or a region needed to be disabled, we'd manually mark that domain as invalid, preventing traffic being routed there.

For multi-region capable services that were stateless and did not have backing services, healthchecks are configured for the services so they would automatically failover when the health checks would fail.

### Latent issues

For some time now, we'd get sporadic reports about LBR not being entirely accurate and routing was deterministic. One of the teams reached out to us to migrate their existing LBR to GBR.  

And that's where I come in - this came up during my oncall shift. As part of the oncall process, the oncall engineer on shift also handles support requests that were
escalated to us. For a LBR, for each domain, we create multiple entries, each record pointing to a load balancer in a different region. For GBR, a record needs to be created to map each country or continent. So assuming you'd want to route a request from each continent, you'd end up creating 8 records - a record for each continent plus a default record. Since we are catering to each continent, you could arguably drop the default record, but the Route 53 documentation states that it would return a "no answer" for queries that it cannot identify the location of, and hence we created a default record that would map to a region.

Now if creating 8 records for a domain was not painful enough, I had to do them for 10 domains, for dev & stage (and later prod) which meant that if I were to do manually via Route 53 console, that's about a 160 records. if you've used the new Route 53 console, you'd knwo the pain - it gets incredibly slow, especially if you have a lot of records.

To support easy creation of Route 53 records, I had created a python script called "route 53 mapper" which reads a YAML file and makes a series of API calls using [boto](https://boto.cloudhackers.com/en/latest/) to create the records. These were invaluable when we moved from ELBs to NLBs (probably a story for another post). In the current context, I figured extending Route 53 mapper is a way to add support for creating the GBR entries.

### Lights, Camera, Action

If there's one philosophy I strongly agree with, is that before you can automate something, you need to understand it.  This was nicely expressed by [Kelsey Hightower](https://twitter.com/kelseyhightower) in the Changelog [Podcast](https://changelog.com/posts/automation-is-the-serialization-of-understanding)

> Automation is the serialization of understanding.

Before you can automate something, you need to understand it. And since I didn't understand how to create and update the records, I tried with a test domain. For a single record LBR, I was able to update the LBR record to GBR without any problems.

However, when I tried to update a multi-record LBR to GBR, I ran into a problem. It seems like it would not possible to have the same domain pointing to a LBR & a GBR at the same time. I opened a support case with Amazon to verify this, and while waiting for a responsed, did some more tests to verify. Ultimately, I came to a conclusion that the easiest way to migrate is to delete all LBR entries, and create corresponding GBR ones. However, this would create downtime and this isn't an option. So after a lot of tests, I concluded that the only way to get a zero-downtime approach to migrating records is to delete all the LBR entries except keep one and then create the rest of the GBR entries. This would have a side effect of some high latency calls and inefficient routing for the time when the other LBR entries are not avaiable but at least the records will resolve. 

The next day, AWS Support confirmed what my conclusion, with a correction to my original plan that I need not convert the single LBR record to a simple routing record and then to GBR, Route 53 would support updating a single LBR to GBR. 

Armed with this, I updated my Route 53 mapper script, tested out on some of my test domains and it worked well. Later in the week, I tried the approach on the services' dev & stage records and it went well without any problems. I documented these and commited the changes to git.

About a month later, the same changes were required for prod and one of the Customer Success Managers who wasn't aware that these steps were required, tried to create the records manually for production. Thankfully, he reached out to me before creating more records. We got on a video call, managed to roll out the migration, moving about 80 records in little under an hour (including time to monitor for changes and prepare the YAML config that was needed) all without any reported errors or downtime.

Hope this little note helps someone in the future.


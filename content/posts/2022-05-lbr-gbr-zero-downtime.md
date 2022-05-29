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

[Amazon Route 53](https://aws.amazon.com/route53/) is a pretty incredible managed Domain Name System(DNS) service. DNS translates domain names to IP addresses and allows for computers to connect to each other. More than just a managed DNS service, Route 53 lets us create records using different routing policies. The routing policy determines how Route 53 responds to a DNS request.

### Primer on Routing Policies

Route 53 supports the following routing policies. 

* Simple routing - Simple routing is a standard DNS record. This is what most other DNS services would do.
* Failover routing - Failover routing policy lets us route traffic to an alternate resource when the primary resource is unhealthy.
* Geolocation routing ("GBR") - Geolocation routing policy lets us route traffic to different resources based on the geographic location of where the request is originating from.
* Latency-based routing ("LBR") - Latency-based routing policy lets us route traffic to various resources based on the best latency that was measured.

The routing policy is selected as you create a record in Route 53.

### Latency-based routing

Latency-based routing ("LBR") is a nifty way of improving the performance of your application. With LBR, AWS automatically and transparently routes traffic to the least-latency resource across the configured regions. AWS does this by determining which region provides the lowest latency and routing the traffic to the region. If you're interested in the details behind how AWS does this, do read their documentation on [How Amazon Route 53 uses EDNS0 to estimate the location of a user](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-edns0).

At work, a lot of the services that did not need multi-region routing were configured with simple routing. For services that could handle multi-region but had backing services and thus could not handle auto-failover would be configured with LBR without health checks. In the case where a failover was required, or a region needed to be disabled, we'd manually mark that domain as invalid, preventing traffic from being routed there.

For multi-region capable services that were stateless and did not have backing services, health checks are configured for the services so they would automatically failover when the health checks would fail.

### Latent issues

For some time now, we'd been getting sporadic reports about LBR not working as expected and some requests were being served from a region that is worse off(purely looking at latency). To improve these latencies, one of the teams reached out to us to migrate their existing LBR records to GBR.  

And that's where I come in - this came up during my on-call shift. As part of the on-call process, the on-call engineer on shift also handles support requests that were escalated to us. For a LBR record, for each domain, we create multiple records with each record pointing to a load balancer in a different region. For GBR, a record needs to be created to map each country or continent to a load balancer in the desired target region. So assuming you'd want to route a request from each continent, you'd end up creating 8 records - a record for each continent plus a default record. Since a record is created mapping each continent, you might wonder why do we need a default record. [Route 53 documentation states](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-geo) that not all IPs would contain geolocation info, and if it receives a DNS request from a location that it cannot identify, Route 53 would return a "no answer". To prevent these errors, a default record is created that maps to our largest region.

Now if creating 8 records for a domain was not painful enough, I had to do them for 10 domains, for dev & stage (and later prod) which meant that if I were to do manually via Route 53 console, that's about a 160 records. if you've used the new Route 53 console, you'd know the pain - it gets incredibly slow, especially if you have a lot of records.

To support easy creation of Route 53 records, I wrote a Python script called "Route 53 mapper". Route 53 mapper reads a YAML file that contains a mapping of a domain to a target destination and makes a series of API calls using [boto](https://boto.cloudhackers.com/en/latest/) to create the records. These were invaluable when we moved from ELBs to NLBs (probably a story for another post). In the current context, I figured extending Route 53 mapper is the best way to complete creating these entries.

### Lights, Camera, Action

If there's one philosophy I strongly agree with, is that before you can automate something, you need to understand it. This was nicely expressed by [Kelsey Hightower](https://twitter.com/kelseyhightower) in the Changelog [Podcast](https://changelog.com/posts/automation-is-the-serialization-of-understanding)

> Automation is the serialization of understanding.

Before you can automate something, you need to understand it. And since I didn't understand how to create and update the records, I tried with a test domain. For a single record LBR, I could update the LBR record to GBR with no problems.

However, when I tried to update a multi-record LBR to GBR, I wasn't able to do so and Route 53 threw an error message

> (InvalidChangeBatch 400: RRSet with DNS name test.sathyabh.at., type A, SetIdentifier ue1, and routing to [continent = (NA, North America)] cannot be created because a non-GEO RRSet with the same name and type already exists).

It seems like it would not be possible to have the same domain pointing to an LBR & a GBR at the same time. I opened a support case with Amazon to verify this, and while waiting for a response, completed some more tests to verify this. I realized that the easiest way to migrate the records is to delete all the LBR entries, and create the corresponding GBR ones. However, this would create downtime and this wasn't an option. After a lot of tests, I concluded that the only way to get a zero-downtime approach is to delete all but one LBR record, update this LBR to a GBR and then create the rest of the GBR entries. This would have a side effect of possibly some high latency calls (since deleting the LBR entries meant all requests are sent to a single region), inefficient routing, and possibly a spike in traffic for the time when the other LBR entries were not available. 

The next day, AWS Support confirmed what I had concluded earlier with a correction to my original plan that I need not convert the single LBR record to a simple routing record and then to GBR, Route 53 would support updating a single LBR to GBR. 

Armed with this knowledge, I updated my Route 53 mapper script, tested it out on some of my test domains and it worked well. Later in the week, I tried this approach on the services' dev & stage records and it went well without any problems. I documented these and committed the changes to git.

About a month later, the same changes were required for prod, and one of the Customer Success Managers, who wasn't aware that these steps were required, tried to create the records manually for production. Thankfully, he reached out to me before creating more records. We got on a video call and rolled out the migration, moving about 80 records in a little under an hour (including time to monitor for changes and prepare the YAML config that was needed) all with no reported errors or downtime.

Hope this helps someone in the future.

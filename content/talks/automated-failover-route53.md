---
title: Enabling automated multi-region failover and failback using Route 53
date: 2022-11-11
publishDate: 2022-11-11
summary: Presented at AWS Community Day 2022 - I talk about using Route 53 and enabling automated multi-region failover and failback using Route 53.
featureimage: https://i.sathyabh.at/ss/talks/route53-records.png
---

Presented at AWS Community Day 2022 - in this talk, I start with a brief about DNS, Route 53, different record types supported by Route 53 and give a brief on how we can setup our infrastructure and applications for handling automated failovers and failback - and what applications are well suited for such a system.

The slides for this talk are available on [Github](https://github.com/sathyabhat/talks-slides) and on my [slides archive page](https://slides.sathyasays.com/). The repo also includes a sample Node.js app running on [AWS App Runner](https://aws.amazon.com/apprunner/) deployed in [two separate regions using CDK](https://github.com/SathyaBhat/talks-slides/tree/main/automated-failover-route53/code). The recording below has a brief on how you can set up the DNS records to route traffic to the closest region and setup health check records so that when application fails in one region, traffic is automatically routed to the other region. Click [here for a direct link](https://youtu.be/NyxZHZhE0M8?t=4233
) to the timestamp when my talk starts.


{{< youtube "NyxZHZhE0M8?t=4269" >}}

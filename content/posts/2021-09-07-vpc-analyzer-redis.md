---
title: Checking for connectivity of ElastiCache Redis instances across peering connections using VPC Analyzer
author: Sathyajith Bhat
type: post
date: 2021-09-13
url: /2021/09/13/vpc-reachability-analyzer-redis
featured_image: 
categories: 
  - DevOps
tags:
  - AWS
  - VPC
  - Cloud

---

It's quite common to work in an environment where you have your VPC connected to with multiple other VPCs, either via VPC Peering or transit gateway, it's no different for me. I was working deploying an application in our inhouse container platform - which is hosted in another account/VPC while connecting to the Redis instances hosted in our VPC/account. I was looking into timeouts connecting to the Redis instance from the application containers, and I figured this would be a good time test out the [VPC Reachability Analyzer](https://aws.amazon.com/blogs/aws/new-vpc-insights-analyzes-reachability-and-visibility-in-vpcs/).

The VPC Reachability Analyzer tool is a network diagnostic tool from AWS. You can access it from the VPC Section of AWS Console. Clicking on Reachability Analyzer, you enter the source, destination, optional intermediaries and click on "Analyze Path" for AWS to trace the path between the source and the destination. 

I wanted to test the connection reachability from the peered connection to the ElastiCache in the private subnet. The first thing I noticed that the destination(and tbh, the source as well) did not have individual services listed. That threw me off, but [Ben Bridts](https://aws.amazon.com/developer/community/heroes/ben-bridts/) pointed out that ElastiCache Nodes would have an ENI attached, so providing the ENI as the destination should work. That said, finding the ENI was not the most straightforward option - I had to head to ElastiCache, pick up the URL of a node, do a dig on node DNS to find the IP address, and search for the IP address on the ENI page on the AWS Console (the Elastic Network Interfaces is shown as an EC2 feature, to make you even more confused).

That said, I created some test paths to check how it works - and the experience was mostly positive. 

For the first test, I accidentally created a path test between a peering connection to our Redis - however, I selected a wrong peering connection and there was peering between the peering connecion I selected and the VPC that the Redis was in. I was pleasantly surprised by the detailed error message, which outlined in detail why the test failed

{{< fancybox "https://images.sbhat.me/ss/reachability-analyzer" "failed-no-path-no-vpc-peering.png" "Error message due to lack of peering and no direct path" "VPC Reachability Analyzer" >}}

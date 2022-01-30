---
title: Checking for connectivity of ElastiCache Redis instances across peering connections using VPC Reachability Analyzer
author: Sathyajith Bhat
type: post
date: 2021-09-13
url: /2021/09/13/vpc-reachability-analyzer-redis
description: The VPC Reachability Analyzer tool is a network diagnostic tool from AWS. In this post I look at how effective the VPC Reachability Analyzer tool to diagnose a network connectivity issue from a VPC peering connection to a private subnet.
featured_image: https://i.sathyabh.at/ss/reachability-analyzer/redis.svg
meta_image: https://i.sathyabh.at/ss/reachability-analyzer/redis.svg
categories: 
  - DevOps
tags:
  - AWS
  - VPC

---

It's quite common to work in an environment where you have your VPC connected to multiple other VPCs, either via VPC Peering or Transit Gateway, it's no different for me. I was working on deploying an application on our in-house container platform. This container platform is hosted in another account/VPC, and it had to connect to the ElastiCache Redis instances hosted in our VPC/account. I was looking into timeouts connecting to the Redis instance from the application containers, and I figured this would be a good time to test out the [VPC Reachability Analyzer](https://aws.amazon.com/blogs/aws/new-vpc-insights-analyzes-reachability-and-visibility-in-vpcs/).

The VPC Reachability Analyzer tool is a network diagnostic tool from AWS. You can access it from the VPC Section of AWS Console. Clicking on Reachability Analyzer, you enter the source, destination, optional intermediaries and click on "Analyze Path" for AWS to trace the path between the source and the destination. 

{{< fancybox "https://i.sathyabh.at/ss/reachability-analyzer" "reachability-analyzer.png" "Finding Reachability Analyzer in the AWS Console" "VPC Reachability Analyzer" >}}

{{< fancybox "https://i.sathyabh.at/ss/reachability-analyzer" "create-analyze-path.png" "Creating a Path Analysis" "VPC Reachability Analyzer" >}}

I wanted to test the connection from the peered connection to the ElastiCache in the private subnet. I noticed the drop-down for destination (and the source ) did not have individual AWS services listed. That threw me off, as I couldn't select ElastiCache there, but [Ben Bridts](https://aws.amazon.com/developer/community/heroes/ben-bridts/) pointed out that each of the ElastiCache nodes would have an ENI attached, so providing the ENI as the destination should work. That said, finding the ENI was not the most straightforward option - I had to head to ElastiCache, pick up the URL of a node, do a dig on node DNS to find the IP address, and search for the IP address on the ENI page on the AWS Console (the Elastic Network Interfaces is shown as an EC2 feature, to make you even more confused). I think there might be avenues to simplify this workflow here.

{{< fancybox "https://i.sathyabh.at/ss/reachability-analyzer" "eni-ec2-feature.png" "Finding the Elastic Network Interface (ENI)" "VPC Reachability Analyzer" >}}


I created some test paths to check how it works, and the experience was mostly positive. 

For the first test, I created a path analysis with the peering connection as the source and the ENI of the ElastiCache Redis as the destination. However, I accidentally selected the wrong peering connection. When the test was completed, it showed a failure, and I was pleasantly surprised by the detailed error message, which outlined why the test failed:

{{< fancybox "https://i.sathyabh.at/ss/reachability-analyzer" "failed-no-path-no-vpc-peering.png" "Error message due to lack of peering and no direct path" "VPC Reachability Analyzer" >}}

For the next attempt, I tried to analyze the path between the correct peering connection and the Redis cluster, and the path trace failed - and yet again, the feedback and error message was pretty detailed in indicating where it was going wrong. It showed the two places where the connection was failing:

- The route table didn't have the correct entries to route traffic from the peering into the private subnet.
- The security group rules were incorrectly configured and were not allowing connections from the peering connection to the Redis port.

{{< fancybox "https://i.sathyabh.at/ss/reachability-analyzer" "destination-unreachable.png" "Error message due to lack of peering and no direct path" "VPC Reachability Analyzer" >}}

Clicking on the details shows the full info about which route table, which security group is preventing the network communication from happening.

{{< fancybox "https://i.sathyabh.at/ss/reachability-analyzer" "details-of-failure.png" "Error message due to lack of peering and no direct path" "VPC Reachability Analyzer" >}}

Once I corrected the errors, the reachability analyzer said all was good! 

{{< fancybox "https://i.sathyabh.at/ss/reachability-analyzer" "path-is-reachable.png" "Reachability Analyzer says reachable" "VPC Reachability Analyzer" >}}


I was still seeing the timeout errors from the application container. And therein lies the trouble with the VPC Reachability Analyzer - if you have multiple routes to a destination, the analyzer seems to consider the fastest path and ignores the failing routes. This is shown briefly when you create an analysis, and it mentions using a particular intermediate component filter to analyze the alternate paths. The intermediate components can be load balancers, NAT gateways, and peering connections but not security groups, ACLs, network interfaces or route tables. In this particular case, there doesn't seem to be a way to show alternate paths. I wish the Reachability Analyzer could use different subnets as an intermediate component filter. This should show the alternate paths where there are multiple routes via different subnets in different availability zones would show all the applicable paths and which ones are failing. 

VPC Reachability Analyzer is still a fantastic tool to debug network connectivity issues, and I can see myself using this often. Path Analysis is charged at the rate of $0.10 per path analysis. And the fact that is done without sending any network traffic along the path is pretty awesome. For more details, you can refer to this re:Invent talk. 

{{< youtube 6DX7p-OirGU >}}

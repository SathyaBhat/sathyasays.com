---
title: Running Folding@Home on AWS with AWS CDK
author: Sathyajith Bhat
type: post
date: 2020-04-26T06:16:24+00:00
url: /2020/04/26/folding-at-home-aws-cdk/
categories:
  - "Tips & How-To's"
tags:
  - AWS
  - AWS CDK
  - Folding@Home

---
[Folding@Home](https://foldingathome.org/about/)(aka FAH) is a distributed computing project. To quote from their website, 

> FAH is a distributed computing project for simulating protein dynamics, including the process of protein folding and the movements of proteins implicated in a variety of diseases. Folding@Home involves you donating your spare computing power by running a small client on your computer. The client then contacts the Folding@Home Work Assignment server, gets some workunits and runs them, You can choose to have it run when only when your system is idle, or have it run all the time. 

While I used to run FAH long, long back - dating back to my [forum days](https://sathyasays.com/about/), I eventually stopped due to lack of proper computing equipment. Recent events with the COVID-19 situation and FAH's projects around it (see [Coronavirus - What we're doing](https://foldingathome.org/2020/03/15/coronavirus-what-were-doing-and-how-you-can-help-in-simple-terms/) and [COVID-19 Small Molecule Screening Simulation](https://foldingathome.org/2020/03/30/covid-19-free-energy-calculations) for details) and the relatively [powerful computer I built recently](https://sathyabh.at/2020/01/19/hellforge-remastered-home-desktop/) meant that I could run FAH on my desktop computer.

Now, I had some extra credits for AWS that were to expire soon and I figured instead of letting them go to waste, I thought to myself maybe I could spin up some EC2 instances and run Folding@Home on them. I started looking at the pricing of the GPU instances - and they were a bit pricier than what I could sustain. Considering this, I selected the c5n.large instance as I didn't need instance and EBS-backed disks would be handy in setting up aa Auto Scaling Group.

To reduce expenses further, I started looking at Spot prices and it turned out, the spot prices were about 68% cheaper as compared to the on-demand prices. Since we don't really care about what happens when the spot termination happens and the ASG will bring the instance count back up, I went with this option. 

{{< figure src="https://i.sathyabh.at/ss/spot-savings.png" title="Spot savings as compared to On-Demand" >}}


The spot pricing trend revealed that the prices had remained stable and just to ensure the spot bids would be fulfilled, I kept the max spot price couple of cents more than the maximum price going then. Initially, the instances were brought up by manually launching them from the AWS Console. Since long I'd been meaning to use [AWS CDK](https://aws.amazon.com/cdk/), this was the perfect opportunity to learn and try to use it. 

The CDK code will bring up a new VPC,a couple of subnets, an ASG and attach a security group to allow for SSH into the instance. The code is not the best, there's a bunch of hard-coding of regions, AMIs, SSH key names, but pull requests to clean up and make it more generic is more than welcome! Check out the code on my [GitHub Repo](https://github.com/SathyaBhat/folding-aws)


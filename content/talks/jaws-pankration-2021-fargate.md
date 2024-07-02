---
title: AWS Fargate instead of Amazon EC2 instances for one-off tasks
date: 2021-11-20
publishDate: 2021-11-20
summary: This talk looks at why you should be using AWS Fargate for one-off tasks. 
---

An updated version of [my talk from re:Invent](/talks/dvc15-fargate-instead-of-ec2/), this talk was given at [JAWS Pankration 2021](https://jawspankration2021.jaws-ug.jp/en/sessions/35/). In this talk I talk about the Serverless approach to ad hoc scripts/tasks by using AWS Fargate as a task runner. I show some sample code for building and deploying AWS Fargate using CDK. Viewers can implement the same process to run virtually task, and be charged only for the time it took to complete the task rather than to have an EC2 instance running all the time. The code is also published online and can be cloned from [GitHub](https://github.com/SathyaBhat/jaws-pankration-2021)

Slides published as code on [GitHub](https://github.com/SathyaBhat/jaws-pankration-2021/blob/main/slides/slides.md).

{{< youtube MEMac-Vl0Yc >}}

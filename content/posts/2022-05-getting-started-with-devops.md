---
title: Migrating Route 53 records from Latency Based Routing to Geolocation routing with zero downtime
author: Sathyajith Bhat
type: post
date: 2022-06-09
url: /2022/06/09/learning-devops
description: I had some fun playing with Route 53's routing policies.
featured_image: https://i.sathyabh.at/ss/r53.svg
meta_image: https://i.sathyabh.at/ss/r53.svg
categories:
  - DevOps
tags:
  - Route 53
  - DNS
  - AWS
---

Look at https://roadmap.sh/devops and start reading up. From this, here's what I think you should do: 
- learn a programming language. Any will do, python is good to start. You need to know enough to write small scripts, not just hello world
- learn to live in terminal: practice how to create files/directories, understand unix permission model (if I ask what does 644 or rwx-w--w- means you should be able to tell me)
- shell scripting is good to have
- learn about managing servers: how to install an OS, how to install software (pick any distro, I would recommend Ubuntu. Others the commands will differ, the principles will be the same)
- learn about how build, run software. Pick any open source software, or build your own, and learn how to package it to deploy. Write small shell scripts to make the 5 things you have to do always in to a script executable script
- learn about containers ("docker" is a tool, containers is the principle). Learn how to package this app you built into a container
- learn about CI/CD principles. Understand the principles. Tools like Jenkins/Gitlab/Github actions will come naturally. Practice how to build your app using CI principles. Then practice how to deploy them using CD.
- Understand how networking works. You don't have to go deep into the kernel level. At the minimum, you need to know about Subnets, routing, interfaces, ports
- Understand OS concepts: understand the Linux folder hierarchy. if someone asks you where the logs are, or how to get a app to run on startup, you should be able to explain these 
- If you're going to pick up Cloud Skills: pick a Cloud,  any cloud. Principle matters, implementation will come from reading the docs
- Understand fundamental pillars of cloud: IAM, Virtual networking
- build something in the cloud. Maybe a manually deploy that app you built onto a cloud VM
- learn some infra as code to automatically do these.

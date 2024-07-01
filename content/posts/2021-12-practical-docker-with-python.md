---
title: Second Edition of Practical Docker With Python is now available
author: Sathyajith Bhat
type: post
date: 2021-12-20T10:00:00+00:00
url: /2021/12/20/practical-docker-with-python-second-edition
summary: The second edition of my book - Practical Docker with Python is now available.
featureimage: https://i.sathyabh.at/ss/practical-docker-with-python-2e.jpg
meta_image: https://i.sathyabh.at/ss/practical-docker-with-python-2e.jpg
categories:
  - General
tags:
  - books
  - Docker
---

About 3 years ago, I wrote my first book - "[Practical Docker with Python](/2018/10/02/so-i-wrote-a-book-presenting-practical-docker-with-python/)". The book focused on the fundamentals of containerization and getting started with Docker.  A few months back, I received an email from my editor at Apress asking me if I'd be interested in doing a second edition of the book. 

Looking back at the book, it had received good feedback, has been cited in different publications and there was some feedback I had received that I always wished I could update the book with, so this was the best chance. After many months of work, the second edition of Practical Docker With Python is available on [SpringerLink](https://bit.ly/practical-docker-2e), Amazon ([US](https://amzn.to/32dTOyD), [India](https://amzn.to/32dTOyD)), [O'Reilly Learning](https://learning.oreilly.com/library/view/practical-docker-with/9781484278154/) (formerly Safari Books Online) and probably every other online bookstore. 

The second edition, much like the first edition, targets people who are new to containerization and want a guided approach to containerizing their application. I start with setting up a Python telegram bot, building and running it as a program, and then continue containerizing the same bot, starting with steps to build the Dockerfile, adding volumes for persisting the data, setting up Docker networks for container networking, and finally multi-container orchestration with Docker Compose. 


{{< fancybox "https://i.sathyabh.at/ss" "practical-docker-with-python-2e.jpg" "Holding my copy of my book - Practical Docker with Python" "Practical Docker with Python" >}}

What's new in this edition is a blurb on getting started with [Windows Subsystem for Linux 2(WSL2)](https://docs.microsoft.com/en-us/windows/wsl/about), an entire chapter dedicated to Continuous Integration, and how a container image becomes from being a local thing to being deployed on an orchestrator like Kubernetes. Writing about Kubernetes was the hardest thing - entire books have been written on it and I certainly didn't want to focus on it, but I hope it gives a taste of what you can do with k8s.

Among the things that were left out include "docker <space> compose", and multi-arch builds using buildx. The next gen docker compose (note: NOT "docker-compose"!) was just too new to be included in the book. But there is a reference to compose spec, and "docker compose" is supposed to be a drop-in replacement, so hopefully, you can swap out the commands. Not including docker compose meant I couldn't include deploying to ECS/other container orchestrators using docker compose.

I hope the second edition is a value add and you like it as much as I enjoyed writing it. Feedback, of course, is always welcome. My Twitter DMs are always open, or you can reach out to me on the channels mentioned in the [contact page](https://sathyabh.at/contact/).
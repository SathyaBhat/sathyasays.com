
---
title: Notes on moving Amazon Linux AMI to Amazon Linux 2
author: Sathyajith Bhat
type: post
date: 2022-05-23
url: /2022/05/23/amazon-linux-to-amazon-linux-2
description: I picked up a task to migrate our base image from Amazon Linux to Amazon Linux 2. Here's what I needed to get it to work.
featured_image: 
meta_image: 
categories:
  - DevOps
tags:
  - Packer
  - AWS
  - AMI
---

Last year around this time, I worked on moving the base AMIs from Amazon Linux to Amazon Linux 2. The Amazon Linux 2 images are baked with a security-hardened base image that is provided by another team. To this hardened image, we tweak some Linux kernel parameters to improve the performance and reliability. Some the changes include increasing the conntrack limits, reserve some ports on boot (by using the `net.ipv4.ip_local_reserved_ports` directive) so that an ephemeral port doesn't use up a port that is needed by a service when it starts (yep, we've run into that), disk-encryption using LUKS and dm-crypt. 


The migration took longer than expected. It should have been painless but Amazon broke some stuff across the distros. In one instance, Amazon Linux had a symlink from `/dev/ephemeral0` to the actual nvme ephemeral device. In Amazon Linux 2 this was no longer present, causing instance boot and consequently Chef(which provisions the instances) to fail. 20 hours and 19 revisions later, I got the AMI to work. Some of the major changes I had noted:

  - boto was no longer available, causing the chef boostrap to fail (reason: boto is used to fetch some scripts from S3)
  - `/dev/ephemeral0` symlink no longer exists, this was a major issue, causing filesystem mounts to fail. I had to add `nofail` to `/etc/fstab` for the filesystem mount to not fail. Without this, the instance wouldn't provision and fail early in cloud-init. This lead to EC2 instance checks to fail.
  - `/etc/crypttab` had to be updated to include `plain,` at the start of line, indicating the filesystem isn't yet encrypted. This was another odd bug that took many hours of obscure searching to find, only to my dismay that [this was reported 5+ years](https://github.com/systemd/systemd/issues/442) back but went unanswered because apparently nobody ever used it as much? 
  - More cleanups on growpart & unwanted mounts/device names (though this isn't a breaking issue or Amazon Linux 2 fault)
  - `dnsmasq` seems to be listening only on `lo` by default. This was causing DNS timeouts, making our tests take as long as 2+ hours to run. Worse was that the `interface=lo` was hidden around lines of commented config, only spotted due to VS Code's syntax highlighter when I was preparing and collecting data for opening a support ticket with AWS. 
  - A bunch of chkconfigs replaced by `systemctl enable`
  - Bunch of `service start` replaced by `systemctl start` - both these due to Amazon Linux 2 bringing in systemd

My knowledge of how cloud-init, disk encryption using custom keys was pretty poor till point, picking up this task made me understand cloud-init, dm-crypt, crypttab a lot better. Thanks Amazon!
---
title: Gain couple of Gigabytes of free space on Linux
author: Sathya
type: post
date: 2010-10-09T00:17:46+00:00
url: /2010/10/09/gain-couple-of-gigabytes-of-free-space-on-linux/
topsy_short_url:
  - http://u.sbhat.me/bzTe0U
categories:
  - "Tips &amp; How-To's"
tags:
  - /dev
  - commands
  - DE
  - file
  - filesystem
  - free
  - Home
  - how-tos
  - IM
  - linux
  - New
  - os
  - partition
  - Partitions
  - root
  - sudo
  - "tips-and-howto's"
  - user
  - ux
  - X

---
> Block size of my partition is 4096 (it can be checked using dumpe2fs command). So reserved space on my partition is about 6,3 Gb and equal missing size from hd command.
> 
> How to change Reserved Block Count
> 
> Reserved Block Count for given partition can be changed using tune2fs command
> 
> <pre>sudo tune2fs -m 0 /dev/sda3</pre>
> 
> where /dev/sda3 is your file system identifier
> 
> -m option sets the percentage of reserved file system blocks (in this case it is being set to 0%)

via [How to gain couple of Gigabytes of free space on Linux?][1].

Important note from the post:

>  **You shouldn’t do this on partitions used by root (especially / and /root) and on partitions used by OS for logging and storing temporary files (e.g. /var and /tmp).**

I think this point should be mentioned at the top of the post, given how many new users don&#8217;t keep separate root (/) and separate home (/home) partitions.

 [1]: http://whileitcompiles.com/linux/how-to-gain-couple-of-gigabytes-of-free-space-on-linux/
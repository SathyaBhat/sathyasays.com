---
title: 'My Laptop Chronicles: Installing openSUSE 10.3 on my Dell Inspiron 1520'
author: Sathyajith Bhat
type: post
date: 2007-12-02T10:38:58+00:00
url: /2007/12/02/my-laptop-chronicles-installing-opensuse-103-on-my-dell-inspiron-1520/
categories:
  - General
tags:
  - linux

---
  When I got my Dell Inspiron, the first thing that I wanted to do was install openSUSE 10.3 on it. After all openSUSE has been serving me well all these years! Because of time restrictions and office workload being too much, I couln't do it. So when the weekend arrived, I decided to install it!



  Since I dont have an Internet connection, downloading it was out of the question, so I had grabbed a copy of last month's Digit magazine which had a Bootable openSUSE10.3 version on it. Initially I was weary, especially with the partitioning and the bootloader settings(I've done this lots of times, my hesistation was because of Dell MediaDirect occupying the first partition of the HDD. But then I just threw all fear and caution out the door, inserted the DVD and booted up my laptop.



  The green “Welcome” openSUSE splash screen is just awesome and put me in the right mood. After clicking on next couple of times, I ran into trouble. The installer's partitioning tool informed me saying the NTFS partition could not be resized, as there were inconsistencies in the filesystem and informed me to do a file system check.



  



  I was puzzled as I'd shutdown Windows cleanly. Still I booted up into Windows, did a checkdisk and then booted back to openSUSE install. Result: Still the same message! Maybe the MediaDirect partition was causing problems?



  So went through my few stack of CDs that I'd bought with m, hoping for a Kubuntu CD so that I could use QTPart. Luckily Kubuntu cd was with me. Started booting with Kubuntu, the progress bar went going on, but then promblem again! I got another weird message, one with I'd never seen before: “Unable to access tty, job control switched off”. I was like :? Thankfully my cell had GPRS(I abuse my phone with GPRS, use it like 17&#215;7(why not 24&#215;7? I've to sleep, you know! :mrgreen: ) A quick googling indicated that there were lot more people suffering the same problem, what's more interesting is that most of the users affected were Sony Vaio or Dell users!



  Problem was that Kubuntu wasn't loading the module, so I had to do a modprobe to load the module, after which Kubuntu booted up well! Launched QTPart, and went about resizing the partition to allocate 30 GB to Linux, Saved the settings, and rebooted into openSUSE install. After this, I had no further problems, install went about smoothly, and I was shocked that openSUSE install finished in 40 minutes flat, including user setup etc! That's awesome, considering that openSUSE traditionally had extremely long install time, easily crossing 1hour to even 1 and half hours! Even more fantastic is that the system boot-up time is really quick, just few seconds more than a clean install of XP. Though I've posted about this in my previous post, I was rather skeptical despite watching the boot charts. So despite the initial hiccup, openSUSE is running great, everything loads up in an instant, including YaST which has a reputation of being a slow-starter. What's more, I haven't even setup a swap partition. So right now openSUSE is running great on my laptop, and it plays my mp3s without having to install any extra codecs. Here's a snap of my desktop.

![](https://i.sathyabh.at/ss/2007/12/opensuse.jpg)
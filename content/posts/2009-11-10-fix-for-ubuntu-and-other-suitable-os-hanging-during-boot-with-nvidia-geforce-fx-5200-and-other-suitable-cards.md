---
title: Fix for Ubuntu (and other suitable OS) hanging during boot with nVidia GeForce FX 5200 (and other suitable cards)
author: Bharath
type: post
date: 2009-11-09T18:33:43+00:00
url: /2009/11/10/fix-for-ubuntu-and-other-suitable-os-hanging-during-boot-with-nvidia-geforce-fx-5200-and-other-suitable-cards/
topsy_short_url:
  - https://u.sbhat.me/gk0a6D
categories:
  - News
tags:
  - 9.10
  - acpi
  - BIOS
  - eye-candy
  - find
  - history
  - Karmic
  - Karmic Koala
  - Koala
  - linux
  - LiveCD
  - MID
  - NVIDIA
  - open source
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  
---
This is one problem that has affected me the most in my history of Linux usage, so far. Imagine, for two full years I just din&#8217;t know that the solution to this problem is so simple. Too late of me to find out. Anyway, better late than never.

So the problem is, with my graphics card GeForce FX 5200, Ubuntu liveCD/post-installation boot will hang mid-way, with the boot-screen freezing or a big set of hexadecimal codes getting emitted. The cause is that ACPI settings, making some conflict (I suppose), with the Intel On-board Chipset. The &#8220;acpi=off&#8221; bppt option does NOT work in Ubuntu. Now, that&#8217;s what everyone suggests only to know it never helps. (Even Sathya suggested it to me)

It does not work because, BIOS settings dominate at the boot time. In other words, boot takes place by the settings in BIOS.So, the Ubuntu boot option &#8220;acpi=off&#8221; makes no sense. So, now does it become clear? You disable ACPI in BIOS!  Wow, that worked like magic for me. Now I am running Ubuntu 9.10 (Karmic Koala) on my PC without any boot problems.

However, shutdown does not work properly. Other things like restart and general things work fine.

So try that comment on whether it works.
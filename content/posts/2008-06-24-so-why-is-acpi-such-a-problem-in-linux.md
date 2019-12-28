---
title: So Why is ACPI Such A Problem in Linux?
author: Sathya
type: post
date: 2008-06-24T10:59:46+00:00
url: /2008/06/24/so-why-is-acpi-such-a-problem-in-linux/
categories:
  - General
tags:
  - acpi
  - AIR
  - BIOS
  - boot
  - cat
  - cover
  - DE
  - dl
  - HAL
  - history
  - IM
  - intel
  - linux
  - Microsoft
  - mount
  - os
  - read
  - rm
  - support
  - ux
  - windows
  - X

---
Anyone who&#8217;s worked on Linux must&#8217;ve come across a fair share of ACPI-related problems &#8211; lockups, standby problems etc. Some of the &#8220;solutions&#8221; is to disable ACPI support by passing the noacpi parameter during boot-up. So why is ACPI so problematic under Linux?

<!--more-->

[Ankit Chaturvedi][1] has this excellent post on this.

A quick excerpt

> **Problem with ACPI**
> 
> So ACPI is a great specification, it lets you put your PC to sleep/suspend and save power and all. But then why does your linux box fail to recover from a suspend-resume cycle? The answer is again MS. ACPI standard was first implemented by Microsoft a long time ago, and due to the popularity of Windows hardware manufacturers chose to get their hardware passed by the Microsoft’s Hardware Compliance Tests. But herein lies the problem. Microsoft’s ACPI implementation differs slightly from the specification, and so came a lot of buggy BIOS’es that don’t fully follow the ACPI specs from Intel, which is what Linux implementation is based upon. So much for the history, now the question is, what does it affect on your system? For Linux developers, this provides a challenge as vendors are reluctant to change their BIOS to conform to Linux.**ACPI In Linux**

> ACPI in Linux is implemented pretty straightforwardly. The ACPI specification says that a ACPI enabled OS must be able to understand AML, the ACPI Machine Language. For the linux-kernel to understand the ACPI Machine Language it needs an interpreter inside the kernel, which amounts to about 72000 lines of code alone and is part of the kernel since the 2.6 series.

Continue Reading the article over at [Dumpyard &#8211; ACPI in depth][2]

 [1]: https://dumpyard.tumblr.com/
 [2]: https://dumpyard.tumblr.com/post/32511294/acpi-in-depth

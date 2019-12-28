---
title: ATI Open vs. Closed-Source AIGLX Performance
author: Sathya
type: post
date: 2007-11-04T09:28:44+00:00
url: /2007/11/04/ati-open-vs-closed-source-aiglx-performance/
categories:
  - News
tags:
  - ASUS
  - bin
  - chipset
  - chm
  - compiz
  - compiz fusion
  - DE
  - Desktop
  - dl
  - driver
  - drivers
  - dual
  - fusion
  - GNOME
  - Gutsy Gibbon
  - IM
  - intel
  - linux
  - os
  - performance
  - rm
  - support
  - testing
  - Ubuntu
  - ux
  - X
  - xp

---
For those that may have missed it, the ATI/AMD fglrx 8.42 display driver that was released last month had introduced AIGLX support. The open-source &#8220;Radeon&#8221; driver for ATI graphics cards going up to the R400 generation has supported AIGLX for quite some time, but the ATI binary display driver hadn&#8217;t until last month. However, one of the complaints about the fglrx implementation of AIGLX is that in the 8.42.3 driver, some are encountering slow performance in Compiz / Compiz Fusion. We have taken an ATI Radeon X800XL 256MB PCI-E graphics card, which is supported by both the Radeon and fglrx drivers, and have compared their Compiz performance in a few different scenarios.

Compiz 0.6.0 was used with Ubuntu 7.10 &#8220;Gutsy Gibbon&#8221; and the Linux 2.6.22 kernel with X server 1.3. The hardware included a PCI Express x16 based ATI Radeon X800XL with 256MB of video memory, an Intel Pentium D 820 (2.80GHz dual-core) processor, 2GB of DDR3-1333 memory, and an ASUS P5E3 Deluxe (Intel X38 Chipset) motherboard. While these tests are not scientific, we had used the Compiz Benchmark plug-in to measure the frame-rate when different Compiz effects were occurring on the desktop. These test scenarios had included the fire effect, water effect, window hovering, and then just idling within the GNOME 2.20 desktop. Testing was done with the stock &#8220;Radeon&#8221; driver that ships with Ubuntu 7.10 and with the fglrx 8.42.3 binary driver.

<a target="_blank" href="http://www.phoronix.com/scan.php?page=article&item=900&num=1">More Here</a>
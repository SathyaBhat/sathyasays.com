---
title: Fix a Frozen System with the Magic SysRq Keys
author: Sathya
type: post
date: 2007-09-14T19:53:14+00:00
url: /2007/09/15/fix-a-frozen-system-with-the-magic-sysrq-keys/
categories:
  - News
tags:
  - boot
  - DE
  - driver
  - dual
  - FOSS
  - IM
  - install
  - linux
  - LV
  - mount
  - os
  - rm
  - Screen
  - tar
  - ux
  - X

---
<p class="post-entry">
  You finally got your Linux environment to crash. <strong><em>Ctrl+Alt+Backspace</em></strong> does nothing, nor do the <strong><em>F-keys</em></strong>. You know you shouldn’t have installed that bad driver, but <em>you did it anyway</em>.
</p>

So you reach for the power button.

**Stop.**

Mashing in the power button to reboot could cause a problem if your hard drive is still being written to, and usually causes more problems than it solves. The Linux kernel includes a secret method of restarting your PC should it ever stop doing its job.

  1. Hold down the **Alt** and **SysRq (Print Screen)** keys.
  2. While holding those down, type the following in order. Nothing will appear to happen until the last letter is pressed: **REISUB**
  3. Watch your computer reboot magically.

What the individual keys do in that sequence are not as important as what it does as a whole: stops all programs, unmounts all drives, and reboots. A lot safer than just cutting the power.

Here it is again: **REISUB**. Remember that, as it will save you a lot of time when you are configuring a system and something gets messed up. Need a mnemonic? Try **Raising Elephants Is So Utterly Boring**.

As an aside, don’t try this if you just want to reboot. A normal reboot, if it can be done, should always be used instead of the **REISUB** keys.

**R-E-I-S-U-B**.

Source & Author: Jacob from [FOSSwire][1]

 [1]: http://fosswire.com/2007/09/08/fix-a-frozen-system-with-the-magic-sysrq-keys/
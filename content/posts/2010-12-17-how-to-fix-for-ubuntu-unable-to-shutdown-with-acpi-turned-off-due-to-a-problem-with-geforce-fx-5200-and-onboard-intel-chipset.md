---
title: '[How-to] Fix for Ubuntu unable to shutdown with ACPI turned off due to a problem with GeForce FX 5200 and OnBoard Intel Chipset'
author: Bharath
type: post
date: 2010-12-16T21:05:04+00:00
url: /2010/12/17/how-to-fix-for-ubuntu-unable-to-shutdown-with-acpi-turned-off-due-to-a-problem-with-geforce-fx-5200-and-onboard-intel-chipset/
topsy_short_url:
  - https://u.sbhat.me/dQsmAE
categories:
  - "Tips &amp; How-To's"
tags:
  - acpi
  - commands
  - linux
  - "tips-and-howto's"
  - Ubuntu

---
**The title might be a little long so let me explain it here.** This is in relation to <a title="Related Post" href="https://sathyasays.com/2009/11/10/fix-for-ubuntu-and-other-suitable-os-hanging-during-boot-with-nvidia-geforce-fx-5200-and-other-suitable-cards/" target="_blank">my post on Ubuntu hanging during boot with nVidia FX 5200</a>. _A brief history:_ I tried to install and boot Ubuntu (all releases till date) with my card, and ACPI settings turned on. The LiveCD boot and the boot after installation, both hang halfway. My previous solution was to  turn off ACPI in BIOS.

That solution did not allow me to shutdown my PC normally. The shutdown was an abrupt one. An abrupt shutdown is never good for a PC. I never liked it that way also. On the other hand, I had to switch acpi on and off, to wok between Windows XP and Ubuntu on my dual boot. This was getting on my nerves. There might also be many other disadvantages/problems, by running Ubuntu ith ACPI switched off.

<a href="https://ubuntuforums.org/showthread.php?t=1168703" target="_blank">This how-to suggested by Paulis321</a> in Ubuntu Forums has actually worked for me. Thanks to him, that now I am able to boot into ubuntu with acpi switched on. The how-to, however, was bettered by me thus:

  1. Turn off ACPI in BIOS. Boot into Ubuntu (preferably, after installation).
  2. Open _&#8220;/etc/modprobe.d/blacklist.conf&#8221;_ in _gedit_ (or any text editor) with root permissions
  3. Add line _&#8220;blacklist intel_agp&#8221;_ anywhere on the file. Save file
  4. Reboot
  5. Turn ACPI back on, in BIOS
  6. Save and Boot

Hope this helps

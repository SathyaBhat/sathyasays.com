---
title: openSUSE 11.2 Milestone 8 And Release Candidates(RC) add boot from USB flash disk option, here’s how to use it
author: Sathya
type: post
date: 2009-10-22T19:24:28+00:00
url: /2009/10/23/opensuse-11-2-milestone-8-and-release-candidatesrc-add-boot-from-usb-flash-disk-option-heres-how-to-use-it/
categories:
  - "Tips & How-To's"
tags:
  - commands
  - DVD
  - file
  - flash
  - flash drive
  - iso
  - KDE
  - linux
  - LiveCD
  - openSuSE
  - openSUSE 11
  - root
  - SUSE
  - terminal
  - "tips-and-howto's"
  - tutorials
  
---
Howdy folks! Been a \*loong\* time since I last posted isn't it? Just been busy with work & travel (won't bore you with the details, just check [my personal blog][1]{#aptureLink_20DGMzo67U}).
  
I've been looking forward to the upcoming openSUSE 11.2 version ( it's no secret that I'm a fan of [openSUSE][2]{#aptureLink_yxkV6H9kot}), but the main problem for me was that I don't like holding onto optical media, and have a 8gig USB flash disk, especially for these things.

Unfortunately  openSUSE has been lacking a install/boot from USB flash drive for quite sometime, upto now that is. The last Milestone (M8) and the first release candidate, RC1 includes support for booting from USB flash disks.

You will need access to a Linux environment, inorder to accomplish this step.

<!--more-->Once you're in Linux, open the terminal. Insert your USB flash disk. ait for few moments  for the flash disk to be detected. Then, switch to root user by typing


  
`su root`

And then type in
  
`dd if=image.iso of=/dev/sdX bs=4M`
  
Replacing image.iso with the full path of the iso file
  
& sdX with your actual device name of your flash drive. Be careful while entering the device name, all data will be wiped out, ensure you've entered the right one!

And, that's about it. Reboot, using the USB flash disk as boot device & voila!

Note: I've tried this with the KDE4 LiveCD version, if anyone else has tried the DVD version please drop a comment!

 [1]: https://sathyabh.at/
 [2]: https://en.opensuse.org/

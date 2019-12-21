---
title: '“Kernel-panic – not syncing : VFS : Unable to mount root fs on unknown-block(X,X)” error in Ubuntu'
author: Bharath
type: post
date: 2009-12-11T09:01:56+00:00
url: /2009/12/11/kernel-panic-not-syncing-vfs-unable-to-mount-root-fs-on-unknown-blockxx-error-in-ubuntu/
categories:
  - "Tips &amp; How-To's"
tags:
  - 9.10
  - boot
  - DE
  - file
  - grub
  - IM
  - Karmic
  - Karmic Koala
  - Koala
  - linux
  - LiveCD
  - menu
  - mount
  - open source
  - os
  - rm
  - root
  - sync
  - syncing
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - unable
  - vm
  - X

---
This one seems to be a really famous problem for most folks in Ubuntu 9.10 Karmic Koala. So I had it too. The problem was on the initrd file. It is a kernel related file needed for booting. So i did a simple thing.

I replaced initrd.img file of my kernel version with &#8220;initrd.lz&#8221; file from the Ubuntu LiveCD and edited my grub.cfg file (equivalent of menu.lst in older Ubuntu releases), to boot using initrd.lz

In other words, wherever there is an entry like initrd.img.2.24-16 or similar just replace it with initrd.lz and in my case I also copied over the vmlinuz file and made necessary entries (just in case). Now, am back in action with Ubuntu. :D
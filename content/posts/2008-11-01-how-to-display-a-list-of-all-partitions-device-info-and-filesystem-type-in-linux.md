---
title: '[How-To] Display A List of All Partitions, Device Info and Filesystem Type In Linux'
author: Sathya
type: post
date: 2008-11-01T04:30:00+00:00
url: /2008/11/01/how-to-display-a-list-of-all-partitions-device-info-and-filesystem-type-in-linux/
categories:
  - "Tips & How-To's"
tags:
  - commands
  - linux
  - tutorials


---
In my previous posts I'd written on <a href="https://sathyasays.com/2008/11/01/how-to-mount-fat32ntfs-partitions-with-read-and-write-support-in-linux-using-command-line/" target="_blank">how to mount your partitions using the mount</a> command. In the post I'd mentioned that you'd have to mention the partition that you want to mount by specifying /dev/device_name as part of the command. The question that would come to your mind is, How do I know which of my partition is on what device? So let me show how to find out which partition is on what device! <!--more--> Like quite a lot of my posts, this involves the Command prompt &#8211; my preferred way of doing. Open the Terminal. Switch to root user by typing 

`su root`. For those distros whose root accounts are disabled(Like Ubuntu) just prefix sudo. Type `fdisk -l` This is what you'll get

>  `[root@shaman]# fdisk -l`
> 
> Disk /dev/sda: 160.0 GB, 160041885696 bytes
  
> 255 heads, 63 sectors/track, 19457 cylinders
  
> Units = cylinders of 16065 * 512 = 8225280 bytes
  
> Disk identifier: 0x0004ed56
> 
> Device Boot      Start         End      Blocks   Id  System
  
> /dev/sda1               1          10       80293+  83  Linux
  
> /dev/sda2   *          11       15091   121135645+   7  HPFS/NTFS
  
> Partition 2 does not end on cylinder boundary.
  
> /dev/sda3           15091       17455    18991317   8e  Linux LVM
  
> /dev/sda4           17456       19456    16073032+   f  W95 Ext'd (LBA)
  
> /dev/sda5           17456       19456    16073001    7  HPFS/NTFS

The ones to note are Device, and System, the others can be ignored. Device indicates which device the particular filesystem is available at, and System indicates the filesystem type. In my case, /dev/sda1 is a Linux boot partition. My First Windows/NTFS drive(ie, Drive C) is available on /dev/sda2. /dev/sda3 is my Linux partition[configured as a LVM, will cover LVM on a future article] and my second NTFS partition is on /dev/sda4. So now I know which partition is available where, and I can go ahead with mounting.

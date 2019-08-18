---
title: '[How-To] Display A List of All Partitions, Device Info and Filesystem Type In Linux'
author: Sathya
type: post
date: 2008-11-01T04:30:00+00:00
url: /2008/11/01/how-to-display-a-list-of-all-partitions-device-info-and-filesystem-type-in-linux/
categories:
  - News
tags:
  - /dev
  - boot
  - cat
  - commands
  - cover
  - Cylinder
  - DE
  - device info
  - distro
  - distros
  - fdisk
  - file
  - filesystem
  - find
  - fstab
  - indic
  - linux
  - LV
  - LVM
  - mount
  - mounting
  - NTFS
  - os
  - partition
  - Partitions
  - rm
  - root
  - show
  - sudo
  - switch
  - tar
  - terminal
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - user
  - ux
  - vm
  - windows
  - X

---
In my previous posts I&#8217;d written on <a href="http://sathyasays.com/2008/11/01/how-to-mount-fat32ntfs-partitions-with-read-and-write-support-in-linux-using-command-line/" target="_blank">how to mount your partitions using the mount</a> command. In the post I&#8217;d mentioned that you&#8217;d have to mention the partition that you want to mount by specifying /dev/device_name as part of the command. The question that would come to your mind is, How do I know which of my partition is on what device? So let me show how to find out which partition is on what device! <!--more--> Like quite a lot of my posts, this involves the Command prompt &#8211; my preferred way of doing. Open the Terminal. Switch to root user by typing 

`su root`. For those distros whose root accounts are disabled(Like Ubuntu) just prefix sudo. Type `fdisk -l` This is what you&#8217;ll get

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
  
> /dev/sda4           17456       19456    16073032+   f  W95 Ext&#8217;d (LBA)
  
> /dev/sda5           17456       19456    16073001    7  HPFS/NTFS

The ones to note are Device, and System, the others can be ignored. Device indicates which device the particular filesystem is available at, and System indicates the filesystem type. In my case, /dev/sda1 is a Linux boot partition. My First Windows/NTFS drive(ie, Drive C) is available on /dev/sda2. /dev/sda3 is my Linux partition[configured as a LVM, will cover LVM on a future article] and my second NTFS partition is on /dev/sda4. So now I know which partition is available where, and I can go ahead with mounting.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/11/01/how-to-display-a-list-of-all-partitions-device-info-and-filesystem-type-in-linux/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-542" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/11/01/how-to-display-a-list-of-all-partitions-device-info-and-filesystem-type-in-linux/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-542" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/11/01/how-to-display-a-list-of-all-partitions-device-info-and-filesystem-type-in-linux/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-542" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/11/01/how-to-display-a-list-of-all-partitions-device-info-and-filesystem-type-in-linux/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/11/01/how-to-display-a-list-of-all-partitions-device-info-and-filesystem-type-in-linux/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
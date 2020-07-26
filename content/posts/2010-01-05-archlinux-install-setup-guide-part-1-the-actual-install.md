---
title: 'ArchLinux Install & Setup Guide – Part 1 – The actual install'
author: Sathya
type: post
date: 2010-01-04T20:39:54+00:00
url: /2010/01/05/archlinux-install-setup-guide-part-1-the-actual-install/
categories:
  - "Tips & How-To's"
tags:
  - '*nix'
  - AIR
  - Arch
  - ArchLinux
  - AWN
  - bin
  - BIOS
  - commands
  - console
  - dl
  - ext3
  - fdisk
  - file
  - filesystem
  - grub
  - guide
  - guides
  - HAL
  - hard disk
  - internet
  - iso
  - linux
  - login
  - menu
  - open source
  - operating systems
  - partition
  - partitioning
  - PHP
  - root
  - show
  - terminal
  - "tips-and-howto's"
  - tutorials
  - VirtualBox
  - vm
  - warning
  - windows
  - xp

---
Been a while since I posted ;) For some strange reason, recently I got an urge to try out [ArchLinux][1]{#aptureLink_BWSwiwROlt}. After much deliberation finally decided to try out ArchLinux again, [in VirtualBox][2]{#aptureLink_YQu9cIpVYm}. My little install guide I compiled as I was reading through the [Official ArchLinux Install Guide][3]{#aptureLink_OrVThoOrTI} + [Beginner's Guide][4]{#aptureLink_AMQvvRytbx}.

Please note: This is highly customized according to \*my\* requirements and nowhere as thorough /generalized as the official guides. Still, it might help you. Here we go &#8211;
  
<!--more-->

Boot off the iso.

First screen you get once you login

![uploadt.jpg][5]

run

<pre>/arch/setup</pre>

to start install

ArchLinux setup starts

![uploads.jpg][6]

Arch comes with a fairly comprehensive install guide &#8211; check it at @ https://wiki.archlinux.org/index.php/Official\_Arch\_Linux\_Install\_Guide

Or if you're stuck without an Internet connection, the install guide is available on the CD, just hit Alt-F6 to spawn a new terminal, and type

<pre>less /arch/docs/official_installation_guide_en</pre>

to open it ( yes the installer gives wrong info, wonder why!)

The install guide then opens

![uploadrh.jpg][7]

Feel free to read it, for it is pretty comprehensive.

For now, lets get on with the Install. Hit Alt-F1 to go back to install screen. As the screen shows, you have lots to do, so lets start one by one

![uploadb.jpg][8]

We'll start with Option 1- Select Source which allows you to choose CD as source or the &#8216;net. If you've chosen the CD install image, choose CD,else if you've downloaded net install image, choose the second option

![uploado.jpg][9]

Next, we move onto Option 2: Set Clock!

Select the region and timezone. We'll select Asia/Kolkata and the proceed to set the time. The next option is where most people select wrong and then whine saying "Linux can't set my time!"

Linux expects the Hardware clock ( your BIOS/Real Time Clock (RTC)) to be set in UTC time and applies timezone offsets according to Region, while Windows expects time to be set at localime. Anyways, for now select localtime

![uploadp.jpg][10]

Confirm the time and correct it, if it is not correct. For now, the time is correct and we shall move ahead

![uploado.jpg][11]

Next comes, what is probably the toughest part of most OS installs, hard disk preparation. Most people are used to Windows style partitions of C:\, D:\ drives, while \*nix OS don't follow that architecture. \*nix treats all devices as files, and so your c:\, D:\ drive gets mapped as funky names like /dev/sda1 /dev/sda2 and so on. While it seems confusing at first, in reality, its not that hard.

/ &#8211; refers to "root" or the topmost structure in the hierarchy.

&#8211; &#8211; dev &#8211; refers to special devices such as hard disks, CD drives, USB devices and what not.

&#8211; &#8211; &#8211; &#8211; /sd &#8211; refers to SCSI device. Earlier the nomenclature was hdx for IDE devices and sdx for SCSI devices, but now SATA devices are designated as sd.

&#8211; &#8211; &#8211; &#8211; &#8211; -a,b.. refers to the hard disk connected (a= first hard disk, b=second hard disk and so on)

&#8211; &#8211; &#8211; &#8211; &#8211; &#8211; &#8211; &#8212; &#8211; &#8211; -1,2.. refers to partitions.

Combine them, you get, /dev/sda as the first hard disk, /dev/sda1 as first partition of your first hard disk

So lets select Hard disk preparation choice. You get another menu

![uploadmo.jpg][12]

Option 1 &#8211; Is probably best if you want to dedicate an entire hard disk to Arch ( in my case, since I'm using a VM anyway). In the context of this guide, this isn't the best option

Option 3- Puts you in the nitty-gritty of partitioning. Lets not get into here either.

We'll jump into Option 2- Manually Partition Hard Disks. Selecting that will launch cfdisk &#8211; and it should show you available hard disks:

![uploadt.jpg][13]

Confirm the hard disk that you want to partition

![uploadz.jpg][14]

So once cfdisk is up, you'll be treated to a barebones interface. Yes, I mean /barebones/.

![uploadx.jpg][15]

Since I don't have any existing partitions, I'll just create one by selecting New -> Prirmary

![uploado.jpg][16]

I'll create a swap partition first ,so I'll allocate 1GB to it

![uploadab.jpg][17]

Add partition to beginning of the drive

![uploadjy.jpg][18]

We'll create another partition &#8211; and allocate all remaining space to it

![uploadu.jpg][19]

Next, mark the type of the partitions &#8211; first is the swap

![uploadq.jpg][20]

On selecting type, you'll get a huge list of values

![uploadif.jpg][21]

Hit enter, and type 82 to choose swap

![uploadxa.jpg][22]

Now,do the same for the other partition, except that you'll have to enter 83 for filesystem type.. So once you're done with partitioning, it should look something like this:

![uploadwv.jpg][23]

Before we're done, we'll have to mark the Linux partition as bootable, so that it handles booting.

![uploadcm.jpg][24]

Finally, choose Write to write all changes to the drive ( so far, nothing has been written, so you can always back out) and then exit.

Now that the partitions have been created, we'll have to assign mount points.

![uploadj.jpg][25]

You'll get a Warning message, just click no and move ahead

![uploadn.jpg][26]

Earlier, I'd mentioned that sda1 is chosen for swap, so lets select swap as the type:

![uploadhv.jpg][27]

![uploadde.jpg][28]

Do the same for other partition, selection ext3 as the type. When asked for the mount point select "/"

Now, lets move on to 4th option, select pakages where you get to choose which packages to install.Arch follows the policy of install bare minimum first, whatever you want later, so for now you get only a barebones console package. Do select base-develop if you wish to do further tinkering

![uploadt.jpg][29]

Just hit OK, wait for a bit, and then you'll be taken back to the main menu. Proceed with installing the packages.

Once install is done, we'll move ahead with configuring the system.Select nano as the editor. Proceed with editing the files only if you know what you're doing!

Otherwise just leave them as it is.

I'll start with editing /etc/rc.conf since I want to change my hostname ( name of my computer)

![uploadr.jpg][30]

Remember: If it doesn't make sense, don't touch it! Hit Ctrl-X and type Y and hit Enter to save changes, else type no.

Before you leave this screen, don't forget to enter a new root password, &#8211; and remember Do NOT forget this password!

Choose done to return to the main menu.

Now for the last step &#8211; to install bootloader. Just select grub ( or none, if you want your existing bootloader to handle it). Once grub config is generated,

nano will open with menu.lst, where you can do any changes, if needed. Hit Ctrl+X and save, if needed

And that's it! Install is completed, choose exit, and type reboot to start your newly installed ArchLinux !

On rebooting you'll be prompted to login. Bear in mean there are no users created yet, except for the root user. So login with username as root and password you entered above.

Part II: Creating a new user, setting up GUI &#8211; coming soon ;)

 [1]: https://wiki.archlinux.org/index.php/Main_Page
 [2]: ../2008/01/22/virtualization-concepts-and-basics-for-dummies/
 [3]: https://wiki.archlinux.org/index.php/Official_Arch_Linux_Install_Guide
 [4]: https://wiki.archlinux.org/index.php/Beginners_Guide
 [5]: https://img109.imageshack.us/img109/568/uploadt.jpg
 [6]: https://img689.imageshack.us/img689/9173/uploads.jpg
 [7]: https://img42.imageshack.us/img42/654/uploadrh.jpg
 [8]: https://img138.imageshack.us/img138/7899/uploadb.jpg
 [9]: https://img138.imageshack.us/img138/7744/uploado.jpg
 [10]: https://img63.imageshack.us/img63/8769/uploadp.jpg
 [11]: https://img63.imageshack.us/img63/7744/uploado.jpg
 [12]: https://img22.imageshack.us/img22/6568/uploadmo.jpg
 [13]: https://img27.imageshack.us/img27/568/uploadt.jpg
 [14]: https://img27.imageshack.us/img27/5136/uploadz.jpg
 [15]: https://img22.imageshack.us/img22/8774/uploadx.jpg
 [16]: https://img130.imageshack.us/img130/7744/uploado.jpg
 [17]: https://img14.imageshack.us/img14/3241/uploadab.jpg
 [18]: https://img14.imageshack.us/img14/9650/uploadjy.jpg
 [19]: https://img683.imageshack.us/img683/9018/uploadu.jpg
 [20]: https://img709.imageshack.us/img709/3633/uploadq.jpg
 [21]: https://img163.imageshack.us/img163/3698/uploadif.jpg
 [22]: https://img163.imageshack.us/img163/6971/uploadxa.jpg
 [23]: https://img12.imageshack.us/img12/6842/uploadwv.jpg
 [24]: https://img12.imageshack.us/img12/4340/uploadcm.jpg
 [25]: https://img97.imageshack.us/img97/499/uploadj.jpg
 [26]: https://img189.imageshack.us/img189/4622/uploadn.jpg
 [27]: https://img189.imageshack.us/img189/3743/uploadhv.jpg
 [28]: https://img121.imageshack.us/img121/3325/uploadde.jpg
 [29]: https://img121.imageshack.us/img121/568/uploadt.jpg
 [30]: https://img691.imageshack.us/img691/2697/uploadr.jpg

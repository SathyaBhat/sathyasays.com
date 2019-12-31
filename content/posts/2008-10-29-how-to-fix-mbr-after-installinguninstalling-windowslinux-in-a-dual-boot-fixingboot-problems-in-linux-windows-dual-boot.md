---
title: '[How To] Fix MBR after installing/uninstalling Windows/Linux in a dual boot'
author: Bharath
type: post
date: 2008-10-29T04:30:08+00:00
url: /2008/10/29/how-to-fix-mbr-after-installinguninstalling-windowslinux-in-a-dual-boot-fixingboot-problems-in-linux-windows-dual-boot/
categories:
  - "Tips &amp; How-To's"
tags:
  
  - linux
  - terminal
  - tutorials

---
Many, who do a dual boot with any Linux and Windows will face the problem of Master Boot Record (MBR). In easier words, one of them (Windows or Linux) wont boot after installing/uninstalling the other. This is a small guide I hope many would find it useful.

**FIXING WINDOWS BOOT AFTER UNINSTALLING LINUX**
  
<!--more-->


  
**For Windows XP:** Boot the installation CD and select repair. Enter your windows installation drive number (shown there) and enter Administrative Password. Now run these two commands there one after the other  &#8212; &#8220;fixmbr&#8221; and &#8220;fixboot&#8221;. Optionally some people also run &#8220;bootcfg /rebuild&#8221;. You're Done.

**For Windows Vista:** Boot from the installation CD/DVD and enter &#8220;Repair Windows&#8221; link at the left hand bottom of the dialog. Then go to command prompt . There run &#8220;bootrec /fixmbr&#8221; and &#8220;bootrec /fixboot&#8221; commands one after the other. That does it.

**FIXING GRUB AFTER INSTALLING WINDOWS**

1.Boot from a LiveCD and open the terminal..

2.There enter `sudo grub` to enter GRUB prompt.

3.Type `find /boot/grub/stage1` to find out your Linux partition.

4.Then use the device name that was output in the next command, say (hd0,1). Then the command would be `root (hd0,1)`.

5. After this, say `setup (hd0)`. Replace hd0 with your hard drive.

Now your GRUB should be installed fine. However, your windows' boot entry may not be in GRUB. You may choose to restore it while still being in your LiveCD or after booting into your hard-drive installed Linux.

To restore it:

1. Open /boot/grub/menu.lst of your Linux partition, in a text editor and get to the bottom where all the list of options to boot are found.

2. Add the following lines with your Windows name in the title and replace (hd0,0) with your own hard drive and partition:

> `title   Windows 95/98/NT/2000<br />
root   (hd0,0)<br />
makeactive<br />
chainloader+1`

3. Save and reboot.

**EDIT:**

**ADDING WINDOWS XP (AND OLDER) OPTIONS TO VISTA'S BOOT LOADER**

After installing Windows XP after Windows Vista and after restoring Vista's bootloader one may find that xp or older windows' options will not be there. For this please make use of a software called [EasyBCD.][1] The installation and operation are self-explainatory. Just click on Add/Remove Entries and add your OS entry. You may also add your linux and mac entries to it. Also there is an option for having a common bootloader using NeoGrub.

 [1]: https://neosmart.net/dl.php?id=1

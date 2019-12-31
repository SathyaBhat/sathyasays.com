---
title: Formatting USB pen drive in Linux using Terminal
author: Sathya
type: post
date: 2007-06-13T16:38:57+00:00
url: /2007/06/13/formatting-usb-pen-drive-in-linux-using-terminal/
categories:
  - "Tips & How-To's"
tags:
  - commands
  - ext3
  - FAT
  - FAT32
  - file
  - filesystem
  - flash drive
  - formatting
  - hard disk
  - linux
  - pen drive
  - pendrive
  - RIA
  - subs
  - sudo
  - terminal
  - "tips-and-howto's"
  - tutorials
  - USB drive
  - USB pen drive

---
Insert your USB pen drive. Let it get detected and mounted. Open Terminal. Type The Following commands
  
1. <span style="font-weight:bold;">dmesg |tail</span> &#8211;> here the &#8216;|' key is the pipe, ie, the key before the backspace key(the upper one, so press shift)
  
You'll get something like

sathya@shaman:~$ dmesg |tail
  
[ 9921.681164] <span style="font-weight:bold;">sda</span>: Write Protect is off
  
[ 9921.681174] <span style="font-weight:bold;">sda</span>: Mode Sense: 23 00 00 00
  
[ 9921.681178] <span style="font-weight:bold;">sda</span>: assuming drive cache: write through
  
[ 9921.709138] SCSI device <span style="font-weight:bold;">sda</span>: 4030464 512-byte hdwr sectors (2064 MB)
  
[ 9921.720951] sda: Write Protect is off
  
[ 9921.720963] sda: Mode Sense: 23 00 00 00
  
[ 9921.720967] sda: assuming drive cache: write through
  
[ 9921.721225] sda:
  
[ 9921.727896] sd 0:0:0:0: Attached scsi removable disk <span style="font-weight:bold;">sda</span>
  
[ 9921.744187] sd 0:0:0:0: Attached scsi generic sg0 type 0
  
Note the terms in <span style="font-weight:bold;">bold. </span>In your system it will be different, maybe sdb or something. Whatever it may be, make sure to substitute it in the commands below, else your hard disk may get formatted.

2. Unmount your pen drive by using
  
<span style="font-weight:bold;">sudo umount /dev/sda</span> (In your case, please substitute sda with the appropriate device, listed above.

3. use the mkfs.vfat command to format to FAT32 filesystem, or mkfs.ext3 to format to ext3 filesystem
  
<span style="font-weight:bold;">sudo mkfs.vfat -n &#8216;Label' -I /dev/sda </span>Replace Label with the name you want the pen drive to have.

4. That's it! When done formatting, you'll be returned to the prompt
  
sathya@shaman:~$ mkfs.vfat -n &#8216;sathya' -I /dev/sda
  
mkfs.vfat 2.11 (12 Mar 2005)
  
sathya@shaman:~$

Remove and insert the pen drive to have mounted again!

---
title: '[How-To]Mounting LVM partitions from a command prompt or a Root Shell'
author: Sathyajith Bhat
type: post
date: 2008-10-01T11:47:45+00:00
url: /2008/10/01/how-tomounting-lvm-partitions-from-a-command-prompt-or-a-root-shell/
categories:
  - "Tips & How-To's"
tags:
  - commands
  - linux


---
Today as I booted into my openSUSE box, for reasons unknown to me, my LVM partitions failed to mount. fsck didn't help, and and LVM based container system meant that I couldn't use the standard mount /dev/sdxx style of mounting as well. With my /home and / configured as a LVM, the root (/) partition was active, but the /home partition was not being mounted, as a result, X and KDM wouldn't start, giving a console login. After a bit of digging around the man files, I found thw lvm manfile and started experimenting(remember, no net access too!) and found out how to mount the LVM'd partitions.



The below set of commands require root privileges so switch over root using
  
`su root`
  
Next, list out all your partitions, type

`linux:/ # lvmdiskscan`

You will get a list of something like this

&nbsp;

File descriptor 3 left open
  
File descriptor 4 left open

```
/dev/dm-0 [ 9.67 GB]
/dev/sda1 [ 78.41 MB]
  
/dev/dm-1 [ 6.44 GB]
/dev/sda2 [ 115.52 GB]

/dev/dm-2 [ 2.00 GB]
  
/dev/sda3 [ 18.11 GB] LVM physical volume
/dev/sda5 [ 15.33 GB]
```

Make a note of `/dev/dm-x`, those are the devices which correspond to the LVM partitions. Also do note the sizes.

Next, type

`lvdisplay`

to show a detailed list of all logical volumes available.

```
lvdisplay | more


LV Name /dev/system/home
VG Name system
LV UUID 1QP9XM-vlKi-umNO-CXvV-TnZN-RCLk-e1FDIr
LV Write Access read/write
LV Status available

# open 1
LV Size 9.67 GB
Current LE 2475
Segments 1
Allocation inherit
Read ahead sectors auto
- currently set to 256
Block device 253:0

Logical volume

LV Name /dev/system/root
  
VG Name system
  
LV UUID D1fKUJ-uU1C-jlVB-4imh-rrgy-FQu0-TC2Ssm
  
LV Write Access read/write
  
LV Status available
  
# open 1

LV Size 6.44 GB
  
Current LE 1649
  
Segments 1
  
Allocation inherit
  
Read ahead sectors auto
  
currently set to 256
  
Block device 253:1

Logical volume;
  
LV Name /dev/system/swap
  
VG Name system
  
LV UUID w5LqIb-xvcr-Xsbk-y3wg-lT3i-LqdN-GFK8Mi
  
LV Write Access read/write
  
LV Status available
  
\# open 0
  
LV Size 2.00 GB
  
Current LE 512
  
Segments 1
  
Allocation inherit
  
Read ahead sectors auto
  
currently set to 256
  
Block device 253:2
```
  
Now from the above set of data we can deduce that my `/home` partition, of **size 9.67 GB** is available as LV group `/dev/system/home` on `/dev/dm-0`

Now that we know where the partition is available, we can proceed with the mounting using the mount command, as
  
`mount /dev/dm-0 /home`
  
And there you go, your LV partition is mounted!

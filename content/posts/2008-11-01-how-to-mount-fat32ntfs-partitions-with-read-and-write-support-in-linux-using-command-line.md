---
title: '[How To] Mount FAT32/NTFS Partitions with read and write support in linux using command-line'
author: Bharath
type: post
date: 2008-11-01T04:30:38+00:00
url: /2008/11/01/how-to-mount-fat32ntfs-partitions-with-read-and-write-support-in-linux-using-command-line/
categories:
  - "Tips &amp; How-To's"
tags:
  - /dev
  - auto-mount
  - Command-line
  - commands
  - DE
  - ext2
  - ext3
  - FAT
  - FAT32
  - file
  - filesystem
  - fstab
  - hard disk
  - Home
  - linux
  - mount
  - mounting
  - NTFS
  - os
  - partition
  - Partitions
  - pysdm
  - read
  - rm
  - root
  - show
  - sudo
  - Super
  - support
  - switch
  - tar
  - terminal
  - "tips-and-howto's"
  - tutorials
  - user
  - ux
  - windows
  - write
  - X

---
Previously I&#8217;d posted on <a href="https://sathyasays.com/2008/10/08/how-to-automount-hard-drive-partitions-everytime-you-login-in-linux/" target="_blank">auto-mounting partitions at startup</a> using pysdm. This post shows how you can do so by making use of mount <a href="https://sathyasays.com/tag/commands" target="_blank">command</a>.

Below steps require root priviliges, so switch to root or prefix sudo to the commands.

For mounting NTFS drives with read and write support, open the terminal and type

`<span style="text-decoration: line-through;">mount  -t ntfs -o nls=utf8,umask=0222 /dev/device_name /where_you_want_to_mount</span>`

> `mount -t ntfs-3g /dev/device_name /where_you_want_to_mount`/

 _Editor&#8217;s note: ntfs has been superseded by ntfs-3g and will mount with read/write privileges. However it may happen that you&#8217;ve created a mount point which requires root priviliges for read/write access. Hence I suggest that you create a mount point for your Windows drives within your /home directory, that way you won&#8217;t be needing root priviliges_

For FAT32 use:

> `mount -t vfat -o umask=000 /dev/device_name /where_you_want_to_mount`

Replace `/dev/device_name` with your hard disk device partition.

Adding these options to /etc/fstab file will result auto mounting of your drives.

_Editor&#8217;s note: I don&#8217;t suggest touching the /etc/fstab unless its really necessary, as fuse takes care of mounting drives perfectly_
  
PS: If someone knows how to mount ext3 drives with read and write support and other commonly used filesystems please post it as a comment. Adding &#8220;user&#8221; to the options didn&#8217;t work for me.
  
__

_Editor&#8217;s note:_
  
For ext2/3 also, the command remains the same with few changes

> `mount -t ext3 -o user /dev/device_name /where_you_want_to_mount`

Again as mentioned above, it may happen that you&#8217;ve created a mount point which requires root priviliges for read/write access and hence you don&#8217;t get read/write access.

Bonus tip: If you don&#8217;t mention -t option, Linux will autodetect the filesystem type.

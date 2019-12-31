---
title: 'How To: Access ext2/ext3 Formatted Linux Partitions in Windows'
author: Sathya
type: post
date: 2008-06-01T16:08:19+00:00
url: /2008/06/01/how-to-access-ext2ext3-formatted-linux-partitions-in-windows/
categories:
  - "Tips &amp; How-To's"
tags:
  - filesystem
  - linux

---


Unlike Linux which can mount and access Windows' FAT, FAT16, FAT32 and NTFS filesystems, Windows is incapable of even acknowledging and detecting a Linux filesystem. Fear not, here are 3 softwares which can help in detecting your Linux partition under Windows

  * [Ext2fsd][1]&#8211; The most capable software of the lot. Has read/write support to your Linux partition. The 0.45 version supports replay of journal of a ext3 filesystem in case of a unclean shutdown of your Linux partition.
  * [Ext2 IFS][2] &#8211; Another very good software. Supports read/write, but doesnt replay the journal of a ext3 filesystem. It actually installs a pure _kernel mode_ file system driver, which means all applications can access your Linux partitions, and it appears in file dialogs of all applications.
  * [Linux Reader][3] &#8211; Like the name says, this is just a reader. Effectively you can't write to it, neither is your partition available as a separate drive. You'll have to open the application, then &#8220;extract&#8221; the file to your Windows. Personally I use this, since the lack of write access means that I can have a little peace of mind about my partition not getting corrupted due to writes(I'm not saying this WILL happen, but better be safe)

If you guys know of any other software then do drop a comment.

Cheers

 [1]: https://ext2fsd.sourceforge.net/index.htm
 [2]: https://www.fs-driver.org/
 [3]: https://www.diskinternals.com/linux-reader

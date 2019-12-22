---
title: Vista + Linux/Ubuntu Dual Boot
author: Sathya
type: post
date: 2007-06-12T14:04:29+00:00
url: /2007/06/12/vista-ubuntu-dual-boot/
categories:
  - News
tags:
  - dualboot
  - linux
  - Ubuntu


---
One of the most teething problems involving Vista is that because of the way Microsoft have changed the booting process, the traditional boot.ini method no longer works. After scouring over the Internet and helping a friend over this, here a simple approach to dual booting.

In this scenario, I&#8217;ve considered that Ubuntu Feisty Fawn was installed first to an ext3 partition. Next,Vista was installed to a NTFS partition(note that here &#8216;m using only 1 hdd, multiple partitions). The Vista install process will overwrite GRUB, leaving you no way of booting into Ubuntu. So after the Vista install, boot into Ubuntu using the live CD.

At the Ubuntu desktop, we are now oing to edit the GRUB menu.lst file. GRUB is the boot loader for Ubuntu. Right now, GRUB doesn&#8217;t know where to look and find Vista. A small edit of the menu.lst file will fix this.

> <font color="#008000"><font face="Courier 10 Pitch">sudo cp /boot/grub/menu.lst /boot/grub/menu.lst_bak</font></font>

This will create a backup of the original menu.lst file &#8212; a file we are now about to change.

Again at the ~$ prompt, type this:

> <font color="#008000"><font face="Courier 10 Pitch">sudo gedit /boot/grub/menu.lst</font></font>

Near the top of this file, you will see a command line that looks like this:

> <font face="Courier New" size="4"><strong>timeout 3</strong></font>

I suggest changing that &#8216;3&#8217; to somthing like &#8217;10&#8217;. This(in seconds) refers to time the boot menu will be displayed you want to choose which OS you would like to boot.

Near the bottom of this file, you will find a line that looks like this:

<font color="#008000"><font face="Courier 10 Pitch">## ## End Default Options ##</font></font>
  
And immediately below that, you will see &#8216;title&#8217; command lines for the various Ubuntu kernel options you currently have available. We are going to now add a new, small &#8216;title&#8217; section.

Immediately below that ## End Default Options ## line, add the following text:

<font face="Courier New" size="4"><strong>title Windows Vista<br /> root (hd0,1)<br /> makeactive<br /> chainloader +1</strong></font>

Please note you are adding this text ABOVE all other Ubuntu title mentions in the file.

Be sure to press the &#8216;Save&#8217; icon so that you save these changes!

That&#8217;s it. You&#8217;re done. When you next boot the machine, don&#8217;t touch a thing and it will default boot into Windows Vista.
  
PS: If you still are not able to boot into Vista, try changin (hd0,1) to (hd0,2). Thanks to [Subbu][1] and [Rajesh][2] for helping me out with trying this out.

 [1]: https://www.xubz.com
 [2]: https://melife.wordpress.com
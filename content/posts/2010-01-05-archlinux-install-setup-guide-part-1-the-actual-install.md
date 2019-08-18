---
title: 'ArchLinux Install & Setup Guide – Part 1 – The actual install'
author: Sathya
type: post
date: 2010-01-04T20:39:54+00:00
url: /2010/01/05/archlinux-install-setup-guide-part-1-the-actual-install/
categories:
  - "Tips &amp; How-To's"
tags:
  - '*nix'
  - /dev
  - AIR
  - Arch
  - ArchLinux
  - AWN
  - bin
  - BIOS
  - boot
  - cat
  - commands
  - console
  - DE
  - dl
  - download
  - ext3
  - fdisk
  - file
  - filesystem
  - free
  - fun
  - grub
  - guide
  - guides
  - HAL
  - hard disk
  - IM
  - install
  - internet
  - iso
  - linux
  - login
  - menu
  - mount
  - move
  - net
  - New
  - open source
  - operating systems
  - os
  - partition
  - partitioning
  - Partitions
  - PHP
  - read
  - rm
  - root
  - Screen
  - show
  - tar
  - terminal
  - "tips-and-howto's"
  - tutorials
  - usb
  - user
  - ux
  - VirtualBox
  - vm
  - warning
  - windows
  - write
  - X
  - xp

---
Been a while since I posted ;) For some strange reason, recently I got an urge to try out [ArchLinux][1]{#aptureLink_BWSwiwROlt}. After much deliberation finally decided to try out ArchLinux again, [in VirtualBox][2]{#aptureLink_YQu9cIpVYm}. My little install guide I compiled as I was reading through the [Official ArchLinux Install Guide][3]{#aptureLink_OrVThoOrTI} + [Beginner&#8217;s Guide][4]{#aptureLink_AMQvvRytbx}.

Please note: This is highly customized according to \*my\* requirements and nowhere as thorough /generalized as the official guides. Still, it might help you. Here we go &#8211;
  
<!--more-->

Boot off the iso.

First screen you get once you login

<img src="https://i1.wp.com/img109.imageshack.us/img109/568/uploadt.jpg?w=740" alt="uploadt.jpg" data-recalc-dims="1" />

run

<pre>/arch/setup</pre>

to start install

ArchLinux setup starts

<img src="https://i1.wp.com/img689.imageshack.us/img689/9173/uploads.jpg?w=740" alt="uploads.jpg" data-recalc-dims="1" />

Arch comes with a fairly comprehensive install guide &#8211; check it at @ http://wiki.archlinux.org/index.php/Official\_Arch\_Linux\_Install\_Guide

Or if you&#8217;re stuck without an Internet connection, the install guide is available on the CD, just hit Alt-F6 to spawn a new terminal, and type

<pre>less /arch/docs/official_installation_guide_en</pre>

to open it ( yes the installer gives wrong info, wonder why!)

The install guide then opens

<img src="https://i1.wp.com/img42.imageshack.us/img42/654/uploadrh.jpg?w=740" alt="uploadrh.jpg" data-recalc-dims="1" />

Feel free to read it, for it is pretty comprehensive.

For now, lets get on with the Install. Hit Alt-F1 to go back to install screen. As the screen shows, you have lots to do, so lets start one by one

<img src="https://i2.wp.com/img138.imageshack.us/img138/7899/uploadb.jpg?w=740" alt="uploadb.jpg" data-recalc-dims="1" />

We&#8217;ll start with Option 1- Select Source which allows you to choose CD as source or the &#8216;net. If you&#8217;ve chosen the CD install image, choose CD,else if you&#8217;ve downloaded net install image, choose the second option

<img src="https://i1.wp.com/img138.imageshack.us/img138/7744/uploado.jpg?w=740" alt="uploado.jpg" data-recalc-dims="1" />

Next, we move onto Option 2: Set Clock!

Select the region and timezone. We&#8217;ll select Asia/Kolkata and the proceed to set the time. The next option is where most people select wrong and then whine saying &#8220;Linux can&#8217;t set my time!&#8221;

Linux expects the Hardware clock ( your BIOS/Real Time Clock (RTC)) to be set in UTC time and applies timezone offsets according to Region, while Windows expects time to be set at localime. Anyways, for now select localtime

<img src="https://i0.wp.com/img63.imageshack.us/img63/8769/uploadp.jpg?w=740" alt="uploadp.jpg" data-recalc-dims="1" />

Confirm the time and correct it, if it is not correct. For now, the time is correct and we shall move ahead

<img src="https://i1.wp.com/img63.imageshack.us/img63/7744/uploado.jpg?w=740" alt="uploado.jpg" data-recalc-dims="1" />

Next comes, what is probably the toughest part of most OS installs, hard disk preparation. Most people are used to Windows style partitions of C:\, D:\ drives, while \*nix OS don&#8217;t follow that architecture. \*nix treats all devices as files, and so your c:\, D:\ drive gets mapped as funky names like /dev/sda1 /dev/sda2 and so on. While it seems confusing at first, in reality, its not that hard.

/ &#8211; refers to &#8220;root&#8221; or the topmost structure in the hierarchy.

&#8211; &#8211; dev &#8211; refers to special devices such as hard disks, CD drives, USB devices and what not.

&#8211; &#8211; &#8211; &#8211; /sd &#8211; refers to SCSI device. Earlier the nomenclature was hdx for IDE devices and sdx for SCSI devices, but now SATA devices are designated as sd.

&#8211; &#8211; &#8211; &#8211; &#8211; -a,b.. refers to the hard disk connected (a= first hard disk, b=second hard disk and so on)

&#8211; &#8211; &#8211; &#8211; &#8211; &#8211; &#8211; &#8212; &#8211; &#8211; -1,2.. refers to partitions.

Combine them, you get, /dev/sda as the first hard disk, /dev/sda1 as first partition of your first hard disk

So lets select Hard disk preparation choice. You get another menu

<img src="https://i2.wp.com/img22.imageshack.us/img22/6568/uploadmo.jpg?w=740" alt="uploadmo.jpg" data-recalc-dims="1" />

Option 1 &#8211; Is probably best if you want to dedicate an entire hard disk to Arch ( in my case, since I&#8217;m using a VM anyway). In the context of this guide, this isn&#8217;t the best option

Option 3- Puts you in the nitty-gritty of partitioning. Lets not get into here either.

We&#8217;ll jump into Option 2- Manually Partition Hard Disks. Selecting that will launch cfdisk &#8211; and it should show you available hard disks:

<img src="https://i2.wp.com/img27.imageshack.us/img27/568/uploadt.jpg?w=740" alt="uploadt.jpg" data-recalc-dims="1" />

Confirm the hard disk that you want to partition

<img src="https://i1.wp.com/img27.imageshack.us/img27/5136/uploadz.jpg?w=740" alt="uploadz.jpg" data-recalc-dims="1" />

So once cfdisk is up, you&#8217;ll be treated to a barebones interface. Yes, I mean /barebones/.

<img src="https://i0.wp.com/img22.imageshack.us/img22/8774/uploadx.jpg?w=740" alt="uploadx.jpg" data-recalc-dims="1" />

Since I don&#8217;t have any existing partitions, I&#8217;ll just create one by selecting New -> Prirmary

<img src="https://i2.wp.com/img130.imageshack.us/img130/7744/uploado.jpg?w=740" alt="uploado.jpg" data-recalc-dims="1" />

I&#8217;ll create a swap partition first ,so I&#8217;ll allocate 1GB to it

<img src="https://i2.wp.com/img14.imageshack.us/img14/3241/uploadab.jpg?w=740" alt="uploadab.jpg" data-recalc-dims="1" />

Add partition to beginning of the drive

<img src="https://i1.wp.com/img14.imageshack.us/img14/9650/uploadjy.jpg?w=740" alt="uploadjy.jpg" data-recalc-dims="1" />

We&#8217;ll create another partition &#8211; and allocate all remaining space to it

<img src="https://i2.wp.com/img683.imageshack.us/img683/9018/uploadu.jpg?w=740" alt="uploadu.jpg" data-recalc-dims="1" />

Next, mark the type of the partitions &#8211; first is the swap

<img src="https://i1.wp.com/img709.imageshack.us/img709/3633/uploadq.jpg?w=740" alt="uploadq.jpg" data-recalc-dims="1" />

On selecting type, you&#8217;ll get a huge list of values

<img src="https://i0.wp.com/img163.imageshack.us/img163/3698/uploadif.jpg?w=740" alt="uploadif.jpg" data-recalc-dims="1" />

Hit enter, and type 82 to choose swap

<img src="https://i1.wp.com/img163.imageshack.us/img163/6971/uploadxa.jpg?w=740" alt="uploadxa.jpg" data-recalc-dims="1" />

Now,do the same for the other partition, except that you&#8217;ll have to enter 83 for filesystem type.. So once you&#8217;re done with partitioning, it should look something like this:

<img src="https://i1.wp.com/img12.imageshack.us/img12/6842/uploadwv.jpg?w=740" alt="uploadwv.jpg" data-recalc-dims="1" />

Before we&#8217;re done, we&#8217;ll have to mark the Linux partition as bootable, so that it handles booting.

<img src="https://i2.wp.com/img12.imageshack.us/img12/4340/uploadcm.jpg?w=740" alt="uploadcm.jpg" data-recalc-dims="1" />

Finally, choose Write to write all changes to the drive ( so far, nothing has been written, so you can always back out) and then exit.

Now that the partitions have been created, we&#8217;ll have to assign mount points.

<img src="https://i1.wp.com/img97.imageshack.us/img97/499/uploadj.jpg?w=740" alt="uploadj.jpg" data-recalc-dims="1" />

You&#8217;ll get a Warning message, just click no and move ahead

<img src="https://i2.wp.com/img189.imageshack.us/img189/4622/uploadn.jpg?w=740" alt="uploadn.jpg" data-recalc-dims="1" />

Earlier, I&#8217;d mentioned that sda1 is chosen for swap, so lets select swap as the type:

<img src="https://i1.wp.com/img189.imageshack.us/img189/3743/uploadhv.jpg?w=740" alt="uploadhv.jpg" data-recalc-dims="1" />

<img src="https://i1.wp.com/img121.imageshack.us/img121/3325/uploadde.jpg?w=740" alt="uploadde.jpg" data-recalc-dims="1" />

Do the same for other partition, selection ext3 as the type. When asked for the mount point select &#8220;/&#8221;

Now, lets move on to 4th option, select pakages where you get to choose which packages to install.Arch follows the policy of install bare minimum first, whatever you want later, so for now you get only a barebones console package. Do select base-develop if you wish to do further tinkering

<img src="https://i0.wp.com/img121.imageshack.us/img121/568/uploadt.jpg?w=740" alt="uploadt.jpg" data-recalc-dims="1" />

Just hit OK, wait for a bit, and then you&#8217;ll be taken back to the main menu. Proceed with installing the packages.

Once install is done, we&#8217;ll move ahead with configuring the system.Select nano as the editor. Proceed with editing the files only if you know what you&#8217;re doing!

Otherwise just leave them as it is.

I&#8217;ll start with editing /etc/rc.conf since I want to change my hostname ( name of my computer)

<img src="https://i1.wp.com/img691.imageshack.us/img691/2697/uploadr.jpg?w=740" alt="uploadr.jpg" data-recalc-dims="1" />

Remember: If it doesn&#8217;t make sense, don&#8217;t touch it! Hit Ctrl-X and type Y and hit Enter to save changes, else type no.

Before you leave this screen, don&#8217;t forget to enter a new root password, &#8211; and remember Do NOT forget this password!

Choose done to return to the main menu.

Now for the last step &#8211; to install bootloader. Just select grub ( or none, if you want your existing bootloader to handle it). Once grub config is generated,

nano will open with menu.lst, where you can do any changes, if needed. Hit Ctrl+X and save, if needed

And that&#8217;s it! Install is completed, choose exit, and type reboot to start your newly installed ArchLinux !

On rebooting you&#8217;ll be prompted to login. Bear in mean there are no users created yet, except for the root user. So login with username as root and password you entered above.

Part II: Creating a new user, setting up GUI &#8211; coming soon ;)

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2010/01/05/archlinux-install-setup-guide-part-1-the-actual-install/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-817" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2010/01/05/archlinux-install-setup-guide-part-1-the-actual-install/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-817" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2010/01/05/archlinux-install-setup-guide-part-1-the-actual-install/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-817" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2010/01/05/archlinux-install-setup-guide-part-1-the-actual-install/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2010/01/05/archlinux-install-setup-guide-part-1-the-actual-install/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://wiki.archlinux.org/index.php/Main_Page
 [2]: ../2008/01/22/virtualization-concepts-and-basics-for-dummies/
 [3]: http://wiki.archlinux.org/index.php/Official_Arch_Linux_Install_Guide
 [4]: http://wiki.archlinux.org/index.php/Beginners_Guide
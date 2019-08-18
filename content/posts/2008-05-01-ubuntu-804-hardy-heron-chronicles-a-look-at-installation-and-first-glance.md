---
title: Ubuntu 8.04 Hardy Heron Chronicles – A Look At Installation and First Glance
author: Sathya
type: post
date: 2008-05-01T14:06:23+00:00
url: /2008/05/01/ubuntu-804-hardy-heron-chronicles-a-look-at-installation-and-first-glance/
categories:
  - News
  - Reviews
tags:
  - 2.22
  - 8.04
  - bin
  - bluetooth
  - boot
  - bootup
  - Canonical
  - cat
  - DE
  - Dell
  - Desktop
  - distro
  - distros
  - driver
  - drivers
  - DVD
  - file
  - find
  - GNOME
  - grub
  - gvfs
  - hardy
  - Hardy Heron
  - Heron
  - Human
  - IM
  - Inspiron
  - install
  - intel
  - iso
  - KDE
  - linux
  - LiveCD
  - LTS
  - mount
  - moving
  - net
  - New
  - newbie
  - NTFS
  - NVIDIA
  - open source
  - openSuSE
  - os
  - partition
  - PolicyKit
  - read
  - review
  - rm
  - root
  - Screen
  - script
  - smb
  - support
  - SUSE
  - tar
  - testing
  - theme
  - Ubuntu
  - Ubuntu 8.04
  - upgrade
  - user
  - ux
  - wallpaper
  - windows
  - Wireless
  - write
  - Wubi
  - X
  - xp

---
Quite a lot of people have been waiting for the latest release of Ubuntu, version 8.04 dubbed the &#8220;Hardy Heron&#8221; &#8211; primarily because it&#8217;s a LTS release. So how does the Hardy Heron stack up? I decided to jump into the Hardy Heron brigade and have a look. Is it worth the upgrade?

Read on to find out more!

### System Specifications

I used my beloved <a href="http://sathyasays.com/2007/12/02/dell-inspiron-1520-review/" target="_blank">Dell Inspiron 1520</a>(Intel Core2Duo T5250 @ 1.5 Ghz, 2 GB DDR2 667 RAM, nVidia 8600m GT, Intel 3945 Pro/Wireless) for testing out the Hardy Heron.

I had a pretty bad time with Gutsy &#8211; <a href="http://sathyasays.com/2007/12/09/fixing-no-sound-bug-on-dell-inspiron-1520-in-ubuntu-gutsy/" target="_blank">no sound</a> despite the sound card being detected, LCD brightness varying as if its possessed etc &#8211; these resulted with me removing Gutsy and going back to openSUSE 10.3.

Also, generally I&#8217;ve always tested the 32-bit versions of most distros. This time I decided to break the tradition and go with the 64-bit version.

<!--more-->

### Installation

One of the most difficult things for a a person new to Linux is the installation, and to simplify this, the wubi project was conceived. Wubi allows you to install Ubuntu inside Windows, as though another Windows application. Canonical has understood the usefulness of this nifty utility, and hence Wubi comes with the Hardy by default.

Since I&#8217;m pretty confident with the traditional installer, I thought I&#8217;ll give wubi a shot, to check out how useful it is for a newbie.

The moment you pop in the CD, the Autorun window pops up with 3 choices &#8211; Demo and Full Installation(ie, boot into the LiveCD), Install within Windows(i.e., using Wubi) and Learn more.

<p style="text-align: center;">
  <a href="http://www.flickr.com/photos/sathyabhat/2456149305/"><img src="http://farm3.static.flickr.com/2260/2456149305_4a85167043_m.jpg" alt="" /></a>
</p>

<p style="text-align: left;">
  Clicking on Install within Windows Brings up another dialog, where you can select which drive, size allocated, username, password etc.
</p>

<p style="text-align: center;">
  <a href="http://www.flickr.com/photos/sathyabhat/2457062430/"><img src="http://farm4.static.flickr.com/3024/2457062430_bc55b333d0_m.jpg" alt="" /></a>
</p>

<p style="text-align: left;">
  Click on install and Bingo! Within 2 minutes, your Ubuntu is ready. Wubi uses grub4dos to create entries for Ubuntu bootup. I was pretty impressed with Wubi, it&#8217;s really easy especially for people new to Linux, and the best thing is &#8211; <strong>you don&#8217;t need to burn the ISO file!</strong> Surprised? You can mount the iso using a virtual drive utility like Alcohol 120%, Daemon Tools, click on install and bam! Do note that this would work only with wubi install. Also, while wubi takes about 2 minutes to install, it doesnot install Ubuntu, rather it creates a script of sorts for automated install. This means once you boot into Ubuntu, you&#8217;ll see the normal screens as you would under traditional install, <strong>BUT WITHOUT</strong> any intervention of the user.
</p>

<p style="text-align: left;">
  Does wubi have any drawbacks? Well as a power user, you will be miffed at the choice &#8211; or rather, lack of, Install size options &#8211; you can choose only 4/5/6/7 GB of space allocated. You also cannot add any extra users.
</p>

<p style="text-align: left;">
  Once the install is done, and you are booted into Ubuntu, where as mentioned above the actual install is done. This is pretty fast, as nothing is being read off the CD/DVD drive, unlike Live CD installs. Once this done, you&#8217;ll have to reboot again(the windows effect?) before you can start using hardy
</p>

### Boot-up and First Impressions

One thing that struck me was Hardy is Very fast at bootup. Gutsy for me was slow, Feisty was ok, but Hardy IS very fast. In fact, it makes Windows XP&#8217;s Bootup after fresh install(which is the fastest) seem slow! Hardy was due to get a theme overall, but it was omitted out, so you&#8217;re stuck with the same dull Human/brown theme with a striking new wallpaper

<p style="text-align: center;">
  <a href="http://www.flickr.com/photos/sathyabhat/2455951321/"><img src="http://farm3.static.flickr.com/2363/2456776456_ff1ccdf5f5_m.jpg" alt="" width="240" height="150" /></a>
</p>

<p style="text-align: left;">
  While at first glance Hardy looks like Gutsy with a new wallpaper, there are various subtle changes which become obvious once you start using it. For instance, the thumbnails of pictures are now automatically displayed, and its much faster than ever. ntfs-3g support is included as usual, meaning your Windows drives can be accessed right away, and you can write to them as well.
</p>

<p style="text-align: left;">
  The introduction of PolicyKit means it simplifies the need to enter the root password. Take for instance, my openSUSE partition was detected, but when I tried to mount it, an authentication screen popped up
</p>

<p style="text-align: center;">
  <a href="http://www.flickr.com/photos/sathyabhat/2455945925/"><img src="http://farm3.static.flickr.com/2286/2455945925_bdc3c7fe07_m.jpg" alt="" width="240" height="195" /></a>
</p>

<p style="text-align: left;">
  Now the nifty thing is that the introduction of &#8220;remember password&#8221; means that next time you want to mount an internal partition you won&#8217;t have to type it each time. Plus if you want only the current session to remember the authorization then just check &#8220;For this session only&#8221; checkbox, for the next session you will be asked for the password.
</p>

<p style="text-align: left;">
  Hardy uses Gnome 2.22 as its Desktop manager. Gnome introduces GVFS, and this feature has been available for KDE users since quite some time now. What this means this that you can access, say files over a Windows Network just by typing smb://<ip-address> in the address bar. Very nice feature to have.
</p>

<p style="text-align: left;">
  <a href="http://www.flickr.com/photos/sathyabhat/2456888870/"><img src="http://farm4.static.flickr.com/3228/2456888870_a27991263e_m.jpg" alt="" /></a> <a href="http://www.flickr.com/photos/sathyabhat/2455950591/"><img src="http://farm4.static.flickr.com/3194/2455950591_a46489e0ac_m.jpg" alt="" width="240" height="150" /></a>
</p>

<p style="text-align: center;">
  <a href="http://www.flickr.com/photos/sathyabhat/2455951321/"><img src="http://farm3.static.flickr.com/2415/2455951321_5ac4ea37d4_m.jpg" alt="" width="240" height="150" /></a>
</p>

<p style="text-align: left;">
  Other subtle changes include renaming of &#8220;Restricted Drivers&#8221; to Driver Manager, so that its easier to find.
</p>

<p style="text-align: left;">
  Overall, Hardy seems really good. I didn&#8217;t face any problems, and for me hardware detection was flawless, right from Video card, to the widescreen 1280&#215;800, to the wireless and bluetooth, all were detected perfectly. I just might dump my default openSUSE 10.3 installation to that of Hardy, for that I&#8217;ll have to test it a little bit more.
</p>

<p style="text-align: left;">
  <p style="text-align: left;">
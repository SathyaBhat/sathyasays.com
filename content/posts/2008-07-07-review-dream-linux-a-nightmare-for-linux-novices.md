---
title: '[Review] Dream Linux – A nightmare for Linux novices'
author: Aditya
type: post
date: 2008-07-07T14:09:34+00:00
url: /2008/07/07/review-dream-linux-a-nightmare-for-linux-novices/
categories:
  - Reviews
tags:
  - apologies
  - Apple
  - boot
  - browser
  - cat
  - codecs
  - comparison
  - compiz
  - compiz fusion
  - cover
  - DE
  - Debian
  - Desktop
  - distro
  - dl
  - download
  - DreamLinux
  - driver
  - drivers
  - Emerald
  - file
  - find
  - Firefox
  - free
  - fusion
  - games
  - GNOME
  - grub
  - hard disk
  - Home
  - icons
  - IM
  - inkscape
  - install
  - internet
  - iso
  - Konqueror
  - linux
  - login
  - media
  - menu
  - mount
  - move
  - Mplayer
  - multimedia
  - net
  - New
  - NTFS
  - open source
  - Opera
  - Operating System
  - operating systems
  - os
  - partition
  - partitioning
  - Partitions
  - review
  - Reviews
  - rm
  - root
  - Screen
  - software
  - sudo
  - synaptic
  - tar
  - terminal
  - testing
  - theme
  - themes
  - Ubuntu
  - user
  - ux
  - wallpaper
  - X

---
_Admin&#8217;s Note: This is a guest post by Aditya. Though this post was drafted on 1st July, my work commitments and rather bad memory prevented this post being published. Due apologies._
  
I know that a title is a bit harsh but I am afraid it is true.
  
First lets get into some technical stuff.
  
Dream Linux is a Debian based distro(like Ubuntu) . It has both Xfce and Gnome interface. I&#8217;m reviewing the Gnome version.

### The Installation

The first screen you get after booting into the CD ask you to choose the interface(Gnome or Xfce)
  
It also has memtest for testing memory but the CD cant be checked for defects, which is a very important feature, since the disk has to be free of defects as it is an operating system.
  
I choose the Gnome interface and booted. Here&#8217;s where I faced my first nightmare. The whole thing is pretty slow. Even after booting completely. I do know that a live CD is slow as it is limited by the optical drive but this was way slower than other live C.D&#8217;s.

<!--more-->


  
<a href="http://cooladi2.pictiger.com/albums/30772/15853128/" target="_blank"><img src="https://i2.wp.com/img6.pictiger.com/f3a/15853128_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>

### The live desktop

After booting the system was pretty slow. The desktop had a few icons and it had a dock bar. There are two installers, one for installing on a thumb drive and one for installing on the hard disk. Here I installed it on the hard disk. The installer is a plus point. It is just a one step installer. First it will ask you to give the root password and next you have to add another user and at the last you have to select the type of partitioning and where to install grub. Now Dream Linux also comes with gparted for editing partitions but gparted couldn&#8217;t detect my hard disk properly and didn&#8217;t start at all. This could be due to the NTFS partition present in it. Next hit the apply button and the process will start. The apply button is greyed out until you setup everything correctly. Now when I was installing, even though I setup every thing the apply button was still greyed out. It took me while to figure it out but you have to give a password for every user. Until the the apply button will remain greyed out and the installer doesn&#8217;t even mention this.
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853121/" target="_blank"><img src="https://i2.wp.com/img6.pictiger.com/c50/15853121_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>

### The One( step installer)

The second nightmare started after hitting the apply button. Just to start installing it took about 2-3 minutes and it took a good 40 minutes to complete installing. Now this is unacceptable as this is a 690 MB distro. Ubuntu, in comparison, installs in just 15 minutes.
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853123/" target="_blank"><img src="https://i2.wp.com/img6.pictiger.com/703/15853123_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>

### Installing(this takes forever)

Ah! So it finally installed
  
After waiting long enough for it to install, I rebooted to check out my new installation. The grub installed by the Dream Linux is a modified version of grub. The background is a DreamLinux wallpaper. The screen gives you two options To start Dream Linux in either Normal mode or Recovery mode. I started it in normal mode and it too a long time to boot but not longer than most Distro&#8217;s so this is acceptable. By default the O.S is set to automatically login the default user &#8220;dreamer&#8221;. The desktop is similar to the live C.D&#8217;s desktop but it is without the installer. The doc bar has everything you need. Dream Linux comes with a control panel and also with the gnome control panel. Dream Linux comes with Compiz Fusion and Emerald. The problem starts with enabling compiz .By enabling Compiz the Doc bar was lost. Now I know some might think that its not such a big deal if the doc bar is lost, but in Dream Linux world it is. The developers have fit everything from file browser to synaptic into the Doc bar and have removed synaptic from the menu. Dream Linux also comes with emerald with the default themes.
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853118/" target="_blank"><img src="https://i1.wp.com/img6.pictiger.com/465/15853118_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>

### The desktop after installation

Now, generally the first thing I do is setup the internet . In Linux having an active internet connection is very useful. So I fire up the terminal and type the command to invoke the pppoe wizard and to my pleasant surprise the wizard had a GUI mode rather than the command line mode. I ran the wizard but to my dismay the net didn&#8217;t work. Then what I realized was that the DNS wasn&#8217;t set. So I try to find where I could set the DNS but I couldn&#8217;t find it anywhere. Then I remembered another way to launch the network configuring utility. First you need to right click the panel and select add to panel then select the network monitoring applet. By double clicking it a window opens which has a button to launch the network configuring utility.
  
After setting every thing up, I launched the Browser Iceweasel (a debranded version of Firefox). The net worked and the default home page was the Dream Linux homepage. It also had a link to the the Debian home page.
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853108/" target="_blank"><img src="https://i1.wp.com/img6.pictiger.com/0d9/15853108_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>
  
**Iceweasel(A debranded version of firefox)**

### Installing the ATI Linux drivers

Normally there is no need to mention the installation but I found a new way to install them I&#8217;m mentioning the installation process.
  
Now first I tried the fglrx drivers from synaptic but they were of no use. Next I downloaded the Drivers from AMD&#8217;s site. Now for the installer to work it needs to be done a root user or through sudo. So to install it the new way just right click the downloaded file and select open with, now click use custom command and type sudo and hit enter. Now wait for the setup to load(this takes some time) after the whole process is over hit ctrl+alt+backspace to restart xserver. After you log back in check under application&#8217;s menu Catalyst Control Center(CCC) should be present. Start CCC to check if the drivers installed correctly.
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853098/" target="_blank"><img src="https://i0.wp.com/img6.pictiger.com/9bb/15853098_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>
  
**Catalyst Control Center in Linux**

### The Bundled Software

Lets take a look at all the software that Dream Linux comes installed with.
  
Lets start with the browser, the default browser is Iceweasel which is a debranded version of Firefox. Dream Linux also comes with Konqueror the popular files/internet browser in Linux.
  
After games multimedia is the most commonly used application of Linux and Dream Linux is oriented towards multimedia. First of the striking features is that it almost no codecs need to be installed. Even the MP3 codecs need not be installed. For managing and playing sound files there&#8217;s Rhythymbox and for editing there&#8217;s mixer
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853134/" target="_blank"><img src="https://i2.wp.com/img6.pictiger.com/8db/15853134_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>
  
**Rhythm Box**
  
For video files there&#8217;s Gxine and Mplayer and there&#8217;s avidemux for editing video&#8217;s .
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853106/" target="_blank"><img src="https://i2.wp.com/img6.pictiger.com/c49/15853106_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>
  
**Gxine**
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853130/" target="_blank"><img src="https://i0.wp.com/img6.pictiger.com/efd/15853130_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>
  
**Mplayer**
  
Next we have have gthumb which is a picture browser and of course the gimp and inkscape for editing pictures
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853104/" target="_blank"><img src="https://i0.wp.com/img6.pictiger.com/f3f/15853104_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>
  
**Gthumb**
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853112/" target="_blank"><img src="https://i1.wp.com/img6.pictiger.com/128/15853112_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>
  
**Inkscape**
  
Here is a picture of the Dream Linux control Panel
  
<a href="http://cooladi2.pictiger.com/albums/30772/15853101/" target="_blank"><img src="https://i0.wp.com/img6.pictiger.com/1bd/15853101_th.jpg?w=740" border="0" alt="" data-recalc-dims="1" /></a>
  
**The Control Panel**
  
Finally it comes with the open office suite.

### Final Verdict

Although its pretty loaded up, its also very sluggish and requires some good amount of Linux knowledge. The only reason I was able to get around it was because it was similar to Ubuntu.
  
I would rate it 6/10 .

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/07/07/review-dream-linux-a-nightmare-for-linux-novices/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-330" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/07/07/review-dream-linux-a-nightmare-for-linux-novices/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-330" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/07/07/review-dream-linux-a-nightmare-for-linux-novices/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-330" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/07/07/review-dream-linux-a-nightmare-for-linux-novices/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/07/07/review-dream-linux-a-nightmare-for-linux-novices/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
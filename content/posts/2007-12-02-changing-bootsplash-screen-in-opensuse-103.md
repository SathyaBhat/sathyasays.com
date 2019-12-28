---
title: Changing bootsplash screen in openSUSE 10.3
author: Sathya
type: post
date: 2007-12-02T10:57:08+00:00
url: /2007/12/02/changing-bootsplash-screen-in-opensuse-103/
categories:
  - "Tips &amp; How-To's"
tags:
  - Arch
  - boot
  - bootsplash
  - Convention
  - DE
  - distro
  - distros
  - download
  - eye-candy
  - file
  - Home
  - IM
  - images
  - install
  - KDE
  - Konqueror
  - laptop
  - linux
  - menu
  - New
  - open source
  - openSuSE
  - os
  - personal
  - Resolution
  - rm
  - root
  - Screen
  - Screen Resolution
  - show
  - Super
  - SUSE
  - switch
  - tar
  - terminal
  - theme
  - themes
  - tutorials
  - user
  - ux
  - VGA
  - write
  - X
  - xp
  - YaST

---
It&#8217;s been a while since I&#8217;ve used openSUSE, as I was without a computer or a laptop for over 4 months. But now that I&#8217;ve got my laptop back, It&#8217;s good to be with openSUSE!

<p class="MsoNormal">
  Alright so let&#8217;s have a look at how to change bootsplash screen. Note that this is written with openSUSE as the target distro, the same steps should work with all distros which have bootsplash package installed, if you don&#8217;t have it installed or are unsure if bootsplash is present, head over to <a href="https://www.bootsplash.org/"><span class="Internetlink1">https://www.bootsplash.org/</span></a> and check it out.
</p>

<p class="MsoNormal">
  Boot splash screens are the screens that show up when you&#8217;re booting up or shutting down Linux. Basically while Linux boots, there are 2 modes-silent mode and verbose mode. In silent mode only the picture is shown, while in verbose mode the pictures as well as boot up messages are shown.
</p>

<p class="MsoNormal">
  The bootsplash actually is a theme. The theme file(or rather theme directory) is stored in /etc/bootsplash/themes/ directory. The theme directory consist of 2 more directories: images and config. In addition to these, the theme directory optionally has<span> </span>animations and<span> </span>bootloader directories/ The directory naming convention is self-explanatory so I will not go into more details into these.
</p>

<p class="MsoNormal">
  <o:p> </o:p>
</p>

<p class="MsoNormal">
  So let&#8217;s get to the action and start changing!
</p>

<p class="MsoNormal">
  <!--more--><o:p>
  
  <br /> </o:p>
</p>

<p class="MsoNormal">
  <strong><em>Step 1: Get the theme!</em></strong>
</p>

<p class="MsoNormal">
  <span> </span>You can get some awesome themes from <a href="https://www.kde-look.org/"><span class="Internetlink1">https://www.kde-look.org</span></a><span> </span>My personal favorites are Fingerprint and Tattoo&#8217;s Girl(search for them in the site mentioned above).
</p>

<p class="MsoNormal">
  <o:p> </o:p>
</p>

<p class="MsoNormal">
  <strong><em>Step 2: Extract the file</em></strong>
</p>

<p class="MsoNormal">
  <span> </span>After downloading the file(most likely to be in .tar.gz or in .bz2 format), extract the archive to your home directory.
</p>

<p class="MsoNormal">
  <p class="MsoNormal">
    <strong><em>Step 3: Copy to right directory</em></strong>
  </p>
  
  <p class="MsoNormal">
    <span> </span>If you are using openSUSE(10.2 and above) then Click on the K Menu, and type Konqueror in the search box and select File Manager(Super User mode).
  </p>
  
  <p class="MsoNormal">
    <a href="https://sathyasays.com/wp-content/uploads/2007/12/fm-superuser1.jpg" title="fm-superuser1.jpg"></a>
  </p>
  
  <p style="text-align: center">
    <a href="https://sathyasays.com/wp-content/uploads/2007/12/fm-superuser1.jpg" title="fm-superuser1.jpg"><img src="https://sathyasays.com/wp-content/uploads/2007/12/fm-superuser1.thumbnail.jpg" alt="fm-superuser1.jpg" /></a>
  </p>
  
  <p class="MsoNormal">
    For other distros, open the terminal and type kdesu konqueror. Enter the root password when prompted. Browse over to /etc/bootsplash/themes/ and copy the theme directory to this directory.
  </p>
  
  <p class="MsoNormal">
    Your theme directory should be as shown in the picture:
  </p>
  
  <p class="MsoNormal" align="center">
    <a href="https://sathyasays.com/wp-content/uploads/2007/12/fm-dir.jpg" title="fm-dir.jpg"><img src="https://sathyasays.com/wp-content/uploads/2007/12/fm-dir.thumbnail.jpg" alt="fm-dir.jpg" /></a>
  </p>
  
  <p class="MsoNormal">
    <strong><em>Step 4: Instruct bootsplash to use the new theme.</em></strong>
  </p>
  
  <p class="MsoNormal">
    <span> </span>Click on YaST2, then on System and click on /etc/sysconfig editor. Then click on the “+” besides System, then on Boot and<span> </span>then on THEME. Under setting of theme text box type the name of the directory.
  </p>
  
  <p class="MsoNormal">
    <a href="https://sathyasays.com/wp-content/uploads/2007/12/yast2-sysconf.jpg" title="yast2-sysconf.jpg"><img src="https://sathyasays.com/wp-content/uploads/2007/12/yast2-sysconf.thumbnail.jpg" alt="yast2-sysconf.jpg" /></a> <a href="https://sathyasays.com/wp-content/uploads/2007/12/theme-setting.jpg" title="theme-setting.jpg"><img src="https://sathyasays.com/wp-content/uploads/2007/12/theme-setting.thumbnail.jpg" alt="theme-setting.jpg" /></a>
  </p>
  
  <p class="MsoNormal">
    <o:p> </o:p>
  </p>
  
  <p class="MsoNormal">
    <em><strong>Step 5: Configure init to use the new splash screen</strong></em>
  </p>
  
  <p class="MsoNormal">
    <span> </span>Open Konsole,<span> </span>switch over to root by typing su root and then enter mkinitrd. If all goes well, you should see the bootsplash: <theme name> (resolution) message as shown in the below screen shot.
  </p>
  
  <p class="MsoNormal">
    <a href="https://sathyasays.com/wp-content/uploads/2007/12/mkinit.jpg" title="mkinit.jpg"></a>
  </p>
  
  <p style="text-align: center">
    <a href="https://sathyasays.com/wp-content/uploads/2007/12/mkinit.jpg" title="mkinit.jpg"><img src="https://sathyasays.com/wp-content/uploads/2007/12/mkinit.thumbnail.jpg" alt="mkinit.jpg" /></a>
  </p>
  
  <p class="MsoNormal">
    Happy tweaking!
  </p>
  
  <p class="MsoNormal">
    <o:p> </o:p>
  </p>
  
  <p class="MsoNormal">
    <o:p> </o:p>
  </p>
  
  <p class="MsoNormal">
    <o:p> </o:p>
  </p>
  
  <p>
    EDIT: While downloading themes, don&#8217;t forget to choose a theme which matches with the bootsplash screen resolution! Else instead of the splash screen, you will be greeted by boot up messages instead. For changing the boot splash resolution, Launch YaST, click on System, Boot Configuration, click on the entry for openSUSE and Click on Edit. At lower end you&#8217;ll see a box for VGA. In this, write the code for the required modes.<br /> Resolution VGA Mode Number
  </p>
  
  <p>
    640&#215;480 785(16-bit), 786(24-bit)
  </p>
  
  <p>
    800&#215;600 788(16-bit), 789(24-bit)
  </p>
  
  <p>
    1024&#215;768 791(16-bit), 792(24-bit)
  </p>
  
  <p>
    1280&#215;1024 794(16-bit), 795(24-bit)
  </p>

---
title: Compiz Fusion on openSUSE 10.3 and nVidia cards
author: Sathya
type: post
date: 2007-12-15T10:27:43+00:00
url: /2007/12/15/compiz-fusion-on-opensuse-103-and-nvidia-cards/
categories:
  - "Tips &amp; How-To's"
tags:
  - 1-click install
  - Arch
  - bin
  - compiz
  - compiz fusion
  - console
  - DE
  - Desktop
  - download
  - driver
  - drivers
  - DVD
  - eye-candy
  - fun
  - fusion
  - GNOME
  - IM
  - install
  - KDE
  - linux
  - NVIDIA
  - Nvidia Drivers
  - open source
  - openSuSE
  - os
  - plugin
  - rm
  - root
  - Screen
  - script
  - SUSE
  - switch
  - tar
  - terminal
  - tutorials
  - Ubuntu
  - user
  - ux
  - X
  - xorg
  - xp

---
In my previous post, I&#8217;d explained on [how to install Compiz Fusion on Ubuntu Fiesty][1]. This post will outline the simple steps for installing Compiz Fusion on openSUSE 10.3. This article is written from an nVidia user&#8217;s point of view.

First, you&#8217;ll have to download nVidia&#8217;s drivers. You can get it, via the [1-click install][2](for [Legacy][3] cards, click [here][4]). I&#8217;d recommend downloading the latest drivers from [nvidia&#8217;s site][5] and doing a manual install of the drivers.

#### _Manual install of nVidia drivers_ 

Pre-requisites:

  * compiler gcc,
  * program make and
  * package kernel-source

<!--more-->You can install these from openSUSE DVD. After these are installed,

Get the drivers from [nvidia&#8217;s site][5] and save it.

Open up the terminal, and su to root by typing `su root`

Switch to console mode by typing `init 3`

Switch directory to where the driver is downloaded and saved

`cd /path/to/where/driver/is/saved`

Run the installer script

`sh NVIDIA-Linux-<arch>-<version>-<build>-<pkg#>.run`

Add the composite, render-accel and ARGB-GLX visuals to xorg.conf`<br />
nvidia-xconfig --composite<br />
nvidia-xconfig --render-accel<br />
nvidia-xconfig --add-argb-glx-visuals -d 24`

#### _Installing Compiz Fusion_ 

For KDE users, here&#8217;s the [1-click installer][6]

For GNOME users, Here&#8217;s the [1-click installer][7]

Install Compiz Manager to autostart compiz: [1-click installer][8]

Installation is done! Just run compiz by Clicking on the Compiz-Fusion Icon

<p align="center">
  <a href="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/compiz-fusion-icon.jpg" title="compiz-fusion-icon.jpg"><img src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2007/12/compiz-fusion-icon.thumbnail.jpg?w=740" alt="compiz-fusion-icon.jpg" data-recalc-dims="1" /></a>
</p>

<p align="left">
  That&#8217;s it! Have fun, explore the different plugins!
</p>

<p align="left">
  Important!: If Compiz keeps crashing on your nvidia card, open /usr/bin/compiz-manager and add &#8220;&#8211;no-libgl-fallback&#8221; to COMPIZ_OPTIONS line. COMPIZ_OPTIONS should look like this now:
</p>

> COMPIZ_OPTIONS=&#8221;&#8211;no-libgl-fallback &#8211;sm-disable &#8211;ignore-desktop-hints ccp &#8211;replace&#8221;

<p align="left">
  &nbsp;
</p>

<p align="left">
  Here&#8217;s some screen shots:
</p>

<p align="left">
  <a href="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/my-desktop.jpg" title="my-desktop.jpg"><img src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2007/12/my-desktop.thumbnail.jpg?w=740" alt="my-desktop.jpg" data-recalc-dims="1" /> </a><a href="https://i0.wp.com/sathyasays.com/wp-content/uploads/2007/12/my-desktop2.jpg" title="my-desktop2.jpg"><img src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2007/12/my-desktop2.thumbnail.jpg?w=740" alt="my-desktop2.jpg" data-recalc-dims="1" /> </a><a href="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/desktop3.jpg" title="desktop3.jpg"><img src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2007/12/desktop3.thumbnail.jpg?w=740" alt="desktop3.jpg" data-recalc-dims="1" /> </a><a href="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/motionblur.jpg" title="motionblur.jpg"><img src="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/motionblur.thumbnail.jpg?w=740" alt="motionblur.jpg" data-recalc-dims="1" /></a>
</p>

<p align="left">
  <a href="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/cf.jpg" title="cf.jpg"><img src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2007/12/cf.thumbnail.jpg?w=740" alt="cf.jpg" data-recalc-dims="1" /></a> <a href="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/cf-water.jpg" title="cf-water.jpg"><img src="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/cf-water.thumbnail.jpg?w=740" alt="cf-water.jpg" data-recalc-dims="1" /> </a><a href="https://i1.wp.com/sathyasays.com/wp-content/uploads/2007/12/fusionfireminimize.jpg" title="fusionfireminimize.jpg"><img src="https://i0.wp.com/sathyasays.com/wp-content/uploads/2007/12/fusionfireminimize.thumbnail.jpg?w=740" alt="fusionfireminimize.jpg" data-recalc-dims="1" /> </a><a href="https://i1.wp.com/sathyasays.com/wp-content/uploads/2007/12/fusioneffect1.jpg" title="fusioneffect1.jpg"><img src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2007/12/fusioneffect1.thumbnail.jpg?w=740" alt="fusioneffect1.jpg" data-recalc-dims="1" /></a>
</p>

<p align="left">
  <a href="https://i2.wp.com/sathyasays.com/wp-content/uploads/2007/12/transparent-cube.jpg" title="transparent-cube.jpg"><img src="https://i0.wp.com/sathyasays.com/wp-content/uploads/2007/12/transparent-cube.thumbnail.jpg?w=740" alt="transparent-cube.jpg" data-recalc-dims="1" /></a>
</p>

<p align="left">
  &nbsp;
</p>

[][7]

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/12/15/compiz-fusion-on-opensuse-103-and-nvidia-cards/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-198" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/12/15/compiz-fusion-on-opensuse-103-and-nvidia-cards/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-198" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/12/15/compiz-fusion-on-opensuse-103-and-nvidia-cards/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-198" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/12/15/compiz-fusion-on-opensuse-103-and-nvidia-cards/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/12/15/compiz-fusion-on-opensuse-103-and-nvidia-cards/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://sathyasays.com/2007/07/01/go-crazy-on-eye-candy-with-compiz-fusion/
 [2]: http://opensuse-community.org/nvidia.ymp
 [3]: http://en.opensuse.org/NVIDIA/Legacy
 [4]: http://opensuse-community.org/nvidia-legacy.ymp
 [5]: http://www.nvidia.com/object/unix.html
 [6]: http://download.opensuse.org/repositories/X11:/XGL/openSUSE_10.3/compiz-fusion-kde.ymp
 [7]: http://download.opensuse.org/repositories/X11:/XGL/openSUSE_10.3/compiz-fusion-gnome.ymp
 [8]: http://download.opensuse.org/repositories/X11:/XGL/openSUSE_10.3/compiz-manager.ymp
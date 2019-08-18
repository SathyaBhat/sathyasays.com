---
title: '[How-to] Snow Plugin in Compiz-Fusion'
author: Bharath
type: post
date: 2009-01-31T19:37:59+00:00
url: /2009/02/01/how-to-snow-plugin-in-compiz-fusion/
categories:
  - "Tips &amp; How-To's"
tags:
  - AIR
  - Arch
  - autumn
  - cairo
  - commands
  - compiling
  - compiz
  - DE
  - Desktop
  - distro
  - distros
  - download
  - Dreamscene
  - exe
  - eye-candy
  - Fedora
  - file
  - find
  - forums
  - fusion
  - git
  - IM
  - install
  - internet
  - linux
  - LV
  - net
  - open source
  - openSuSE
  - os
  - plugin
  - read
  - RIA
  - rm
  - Sabayon
  - snow
  - SUSE
  - terminal
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - user
  - wallpaper
  - X

---
After a long time&#8217;s search over the internet for many days I finally figured out how to do this. Many may know this already but many may not too. And since I hate to compile programs from sourceI have found here a method that involves less of actual compiling. Since am a ubuntu user I only have tried this in ubuntu and not other distros.

**STEPS**

1. Install these packages:

compiz-bcop

compiz-dev

compizconfig-settings-manager

build-essential

libtool

libglu1-mesa-dev

libxss-dev

libcairo2-dev

git-core

2. You need a working directory say ~/compiz

3. When in your working directory, in terminal, execute this command:

> git clone git://anongit.compiz-fusion.org/fusion/plugins/snow

4. Download [this][1] file and extract its contents to your working directory

5. In your working directory now there will be a folder called snow. Change to that folder (~/compiz/snow in my case)

6. Execute these three commands one after the other:

> make
> 
> make clean
> 
> make install

7. Now in your CompizConfig Settings Manager you can find the snow plugin and activate it.

This may sort of resemble a dreamscene on your desktop and i really like it a lot. A snowy wallpaper could be suitable.

A small variant of this plugin called Autumn Plugin is [here][2] (Thanks to Patrick Fisher and ubuntu forums)

Thanks to elgilicious and ubuntu forums for [this][3]

_Ed&#8217;s note: Do we really need all of this ?  openSUSE, Fedora, Sabayon &#8211; all had Snow plugin without having to do any of this_

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/02/01/how-to-snow-plugin-in-compiz-fusion/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-677" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/02/01/how-to-snow-plugin-in-compiz-fusion/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-677" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/02/01/how-to-snow-plugin-in-compiz-fusion/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-677" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/02/01/how-to-snow-plugin-in-compiz-fusion/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/02/01/how-to-snow-plugin-in-compiz-fusion/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://oreaus.googlepages.com/snow.tar
 [2]: http://ubuntuforums.org/showthread.php?p=3792520
 [3]: http://ubuntuforums.org/showthread.php?t=768804
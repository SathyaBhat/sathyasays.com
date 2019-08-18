---
title: Fedora 8 and Compiz Fusion on ASUS eeePC 701
author: Sathya
type: post
date: 2008-01-24T18:39:56+00:00
url: /2008/01/24/fedora-8-and-compiz-fusion-on-asus-eeepc/
categories:
  - "Tips &amp; How-To's"
tags:
  - applications
  - ASUS
  - bin
  - blog
  - boot
  - cat
  - compiz
  - compiz fusion
  - DE
  - Dell
  - Desktop
  - driver
  - drivers
  - DVD
  - eeePC
  - Fedora
  - file
  - find
  - Firefox
  - free
  - fusion
  - GNOME
  - grub
  - IM
  - install
  - intel
  - internet
  - keyboard
  - linux
  - LV
  - MBR
  - MID
  - Mobile
  - Mplayer
  - net
  - open source
  - os
  - partition
  - partitioning
  - Pidgin
  - read
  - Screen
  - Sun
  - support
  - tar
  - Thunderbird
  - tutorials
  - update
  - user
  - ux
  - VGA
  - web
  - X
  - xp
  - yum

---
Almost everyone would be knowing about [ASUS eeePC][1] by now. For the uninitiated, The ASUS eee PC is a subnotebook. The eeePC is powered by a 900 MHz Intel Celeron-M ULV 353 processor, features 512MB of DDR2 RAM and uses Xandros as it&#8217;s OS and has an Integrated Intel GMA 900 as its graphics processor. The GMA 900 means that technically the eeePC is capable of running Compiz Fusion. So has anyone done this?

Yes! Someone has! Fred Welland, who received an ASUS eeePC for his birthday according to his blog, has gone ahead and installed Fedora 8 on his eeePC and has mentioned that Compiz and Compiz Fusion are running well on the eeePC.

Here are some excerpts from his [Blog:][2]

> I got a eeePC for my birthday, in mid-November 2007. It is a wonderfull little machine, that is a nice compliment to my Dell Latitude D820 and various and sundry desktops. The top of this page will be devoted to how I installed Fedora 8 on my eeePC. The bottom part of the page relates my experience with eeePC in general.
> 
> ### Fedora 8 Install Goals
> 
> <!--more--> 1 to 1.5 GB Fedora 8 install
> 
>   * Full GNOME support
>   * Basic Internet/Web Tools: firefox, pidgin, thunderbird
>   * 1GB + free space for user files
> 
> Things that would be nice to have:
> 
>   * COMPIZ/Fusion support
>   * working mplayer install (that can play DVDs)
>   * basic office like applications (word processing, maybe a simple draw widget)
>   * CISCO VPN support
> 
> ### The Install
> 
> After partitioning, the install was rather dull &#8212; just your basic Fedora install. Here are some things I did:
> 
>   * Allowed GRUB to go to the MBR.
>   * Selected &#8220;cutomize packages&#8221;
>   * Scanned each package category and eliminated package I did not want. I focussed on keeping things &#8216;thin&#8217; &#8212; I can always yum up things later.
>   * You may consider installing some of the developement stuff &#8212; these things will be needed later. Scan the list of development packages and pick the ones that seem useful.
> 
> <span style="font-weight: bold">NOTE</span>: I did the install using only the stock eeePC keyboard, touch pad and screen. Which is OK, but can be a bit tedius, because you (may) have to use the touchpad and mouse button exclusively for package selections and de-selections. At first I was using the arrow keys to navigate the lists up and down, and the space bar to select or de-select a package. <span style="font-style: italic">This combination caused the installer to crash &#8212; it happened three times at slightly different points</span>. Everything was fine, when I only used the the touchpad.
> 
> ### On First Boot
> 
> My eeePC with F8 booted up just find, and dumped me into the firstboot wizard. Here are the things I did:
> 
>   * set SELinux to disabled
>   * turned off the fire wall
>   * tinkered with network settings a bit (mainly setting to DHCP) &#8212; this is largely useless cause the network stuff isn&#8217;t going to work untill installing some drivers.
>   * made a user account.
>   * reboot (&#8217;cause the installer/start screen needed too).
> 
> ### Video
> 
> Lspci on my eeePC says that I have a `VGA compatible controller: Intel Corporation Mobile 915GM/GMS/910GML Express Graphics Controller (rev 04)` . This controller has good linux support and works more or less out of the box.

> ### Compiz/Fusion

> Compiz and Compiz/Fusion work quite well.

> ### Sound

> Sound works out of the box. No tweaking is really needed.

For those interested, do read his [blog][2], he&#8217;s kept it updated

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/01/24/fedora-8-and-compiz-fusion-on-asus-eeepc/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-246" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/01/24/fedora-8-and-compiz-fusion-on-asus-eeepc/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-246" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/01/24/fedora-8-and-compiz-fusion-on-asus-eeepc/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-246" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/01/24/fedora-8-and-compiz-fusion-on-asus-eeepc/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/01/24/fedora-8-and-compiz-fusion-on-asus-eeepc/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://eeepc.asus.com/
 [2]: http://mysite.verizon.net/vze2j8bn/eeePC-F8.html
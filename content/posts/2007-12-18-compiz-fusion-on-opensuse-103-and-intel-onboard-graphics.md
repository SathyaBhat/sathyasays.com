---
title: Compiz Fusion on openSUSE 10.3 and Intel onboard graphics
author: Sathya
type: post
date: 2007-12-18T13:48:55+00:00
url: /2007/12/18/compiz-fusion-on-opensuse-103-and-intel-onboard-graphics/
categories:
  - "Tips &amp; How-To's"
tags:
  - 1-click install
  - AA
  - bin
  - chipset
  - compiz
  - compiz fusion
  - DE
  - Desktop
  - download
  - eye-candy
  - find
  - fusion
  - GNOME
  - install
  - intel
  - KDE
  - linux
  - onboard
  - open source
  - openSuSE
  - os
  - RIA
  - rm
  - Screen
  - sudo
  - SUSE
  - terminal
  - tutorials
  - user
  - X
  - xorg

---
Contrary to what most people think, it is possible to get all those effects on their Intel based onboard graphics. Now I&#8217;ve helped a few friends to get Compiz Fusion running on their Intel cards, and I was requested by them to post this tutorial, so here it goes.

First up, download the required Compiz Fusion packages via 1-click install; Here are the links:
  
[
  
1-Click Installer for KDE][1]

[1-Click Installer for GNOME][2]

[1-Click Installer for Compiz Manager][3]

We&#8217;ll have make some changes to /etc/X11/xorg.conf as well.

<!--more-->

So open the Terminal and type

> kdesu kate /etc/X11/xorg.conf &#8211;> This is for KDE users
> 
> gksudo gedit /etc/X11/xorg.conf &#8211;> This is for GNOME users

Now scroll down to Section &#8220;Module&#8221; section and check if the below are present. If not, add them.

> `Section "Module"<br />
Load         "dri"<br />
Load         "glx"<br />
Load         "dbe"`

Add these to Section &#8220;Device&#8221;

> `Option      "XAANoOffscreenPixmaps" "true"<br />
Option      "DRI"     "true"<br />
` 

Add these to Section &#8220;ServerLayout&#8221;

> `Option      "AIGLX" "true"`

Make sure Section &#8220;DRI&#8221; looks like this

> `Group      "video"  Mode       0660`

Finally, add this to Section &#8220;Extensions&#8221;

> `Option "Composite" "Enable"`

Next, we&#8217;ll have to modify /usr/bin/compiz-manager to ensure that Indirect Rendering is done. For that, open Terminal and type

> kdesu kate /usr/bin/compiz-manager &#8211;> For KDE Users
> 
> gksudo gedit /usr/bin/compiz-manager &#8211;> For GNOME Users

Scroll down to COMPIZ\_OPTIONS and add &#8211;indirect-rendering. So now, your COMPIZ\_OPTIONS should look something like

COMPIZ_OPTIONS=&#8221;&#8211;indirect-rendering &#8211;sm-disable &#8211;ignore-desktop-hints ccp &#8211;replace&#8221;
  
Also, For GMA X3000/3100/ 965 Chipset users, Find this section

> \# blacklist based on the pci ids
  
> \# See http://wiki.compiz-fusion.org/Hardware/Blacklist for details
  
> T=&#8221; 1002:5954 1002:5854 1002:5955&#8243; # ati rs480
  
> T=&#8221;$T 1002:4153&#8243; # ATI Rv350
  
> T=&#8221;$T 8086:2982 8086:2992 8086:29a2 8086:2a02 8086:2a12&#8243; # intel 965
  
> BLACKLIST_PCIIDS=&#8221;$T&#8221;
  
> unset T

And Change this to

> \# blacklist based on the pci ids
  
> \# See http://wiki.compiz-fusion.org/Hardware/Blacklist for details
  
> T=&#8221; 1002:5954 1002:5854 1002:5955&#8243; # ati rs480
  
> T=&#8221;$T 1002:4153&#8243; # ATI Rv350
  
> \# T=&#8221;$T 8086:2982 8086:2992 8086:29a2 8086:2a02 8086:2a12&#8243; # intel 965
  
> BLACKLIST_PCIIDS=&#8221;$T&#8221;
  
> unset T

That&#8217;s about enough tweaking! To launch compiz-fusion, at the terminal type

> compiz-manager

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/12/18/compiz-fusion-on-opensuse-103-and-intel-onboard-graphics/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-210" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/12/18/compiz-fusion-on-opensuse-103-and-intel-onboard-graphics/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-210" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/12/18/compiz-fusion-on-opensuse-103-and-intel-onboard-graphics/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-210" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/12/18/compiz-fusion-on-opensuse-103-and-intel-onboard-graphics/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/12/18/compiz-fusion-on-opensuse-103-and-intel-onboard-graphics/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://download.opensuse.org/repositories/X11:/XGL/openSUSE_10.3/compiz-fusion-kde.ymp
 [2]: http://download.opensuse.org/repositories/X11:/XGL/openSUSE_10.3/compiz-fusion-gnome.ymp
 [3]: http://download.opensuse.org/repositories/X11:/XGL/openSUSE_10.3/compiz-manager.ymp
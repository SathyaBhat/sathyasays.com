---
title: Wireless Networking Blues? Get rid of NetworkManager, Install Wicd
author: Sathya
type: post
date: 2009-03-02T07:17:48+00:00
url: /2009/03/02/wireless-networking-blues-get-rid-of-networkmanager-install-wicd/
categories:
  - "Tips &amp; How-To's"
tags:
  - Arch
  - boot
  - DE
  - Debian
  - distro
  - distros
  - Fedora
  - Gentoo
  - IM
  - install
  - KDE
  - KDE 4.2
  - KDE4
  - move
  - net
  - NetworkManager
  - open source
  - os
  - read
  - Sabayon
  - Sabayon 4
  - show
  - tar
  - Ubuntu
  - update
  - wicd
  - Wireless
  - X

---
I&#8217;ve jsut about had it with NetworkManager. Everytime I update my system I have to bite my nails wondering whether the update will break my wireless. I&#8217;ve posted earlier about my problems with NetworkManager and on howto fix it, there&#8217;s the best way to fix it: get rid of it.

Yeah, get rid of NetworkManager, install Wicd.

Here&#8217;s how:

<!--more-->Installing in Ubuntu, Debian, Fedora, Arch, Slackware & Gentoo:

Head over to [this page][1] to read up on installing wicd on each of these distros.

Sabayon 4:

Install wicd from using equo
  
`equo install wicd`
  
Next, remove NetworkManager so that it no longer the default tool for managing network connections
  
`rc-update del NetworkManager default boot`
  
Make wicd the default tool for managing networks
  
`rc-update add wicd default`

Also we&#8217;ll add an entry to startup so that wicd starts automatically. Have a look at the video below, that will show you how you can do so.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/03/02/wireless-networking-blues-get-rid-of-networkmanager-install-wicd/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-708" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/03/02/wireless-networking-blues-get-rid-of-networkmanager-install-wicd/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-708" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/03/02/wireless-networking-blues-get-rid-of-networkmanager-install-wicd/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-708" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/03/02/wireless-networking-blues-get-rid-of-networkmanager-install-wicd/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/03/02/wireless-networking-blues-get-rid-of-networkmanager-install-wicd/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://wicd.sourceforge.net/download.php
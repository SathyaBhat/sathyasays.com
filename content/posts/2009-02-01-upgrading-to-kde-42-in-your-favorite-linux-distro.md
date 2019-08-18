---
title: Upgrading to KDE 4.2 in your favorite Linux distro
author: Sathya
type: post
date: 2009-01-31T18:56:10+00:00
url: /2009/02/01/upgrading-to-kde-42-in-your-favorite-linux-distro/
categories:
  - News
tags:
  - Arch
  - ArchLinux
  - community
  - DE
  - Debian
  - Desktop
  - desktop environment
  - distro
  - distros
  - Fedora
  - Fedora 10
  - file
  - forums
  - IM
  - install
  - KDE
  - KDE 4.2
  - KDE4
  - linux
  - media
  - Meta
  - move
  - net
  - openSuSE
  - openSUSE 11
  - openSUSE 11.0
  - opensuse 11.1
  - os
  - PolicyKit
  - repo
  - repos
  - rm
  - root
  - Sabayon
  - Sabayon 4
  - sudo
  - SUSE
  - switch
  - tar
  - terminal
  - testing
  - Unity
  - update
  - upgrade
  - upgrading
  - ux
  - warning
  - Wireless
  - X
  - yum

---
Couple of days ago I&#8217;d posted about [KDE 4.2 being released][1].  As much as I wanted to upgrade KDE 4.2, I couldn&#8217;t do so immediately as it was not available in official Repos, the community repos had the RC version. Everyday I would do a equo search kde-meta hoping that I&#8217;d see the KDE 4.2 branch, and guess what it was available today :D

<!--more-->Here&#8217;s a quick roundup on installing/upgrading to KDE 4.2 on some popular distros:

**Sabayon 4:**

First switch to root. For that, type
  
`su root`
  
next,
  
Just open up the terminal and type

> `equo update`

That updates the repo to have the latest packages. Now most probably you&#8217;ll have to update equo since the update has the latest version of equo. So next type

> `equo install equo`

This will update equo, entropy and Spritz to latest version. Certain config files will have to be updated, so just type

> `equo update conf`

And now, finally update to KDE 4.2 by typing

> `equo install kde-meta-4.2.0`

And that&#8217;s it! Your KDE will be updated to KDE 4.2.0!

**openSUSE:**

Click on the below 1-click links to upgrade:
  
[openSUSE 11.1][2] | [openSUSE 11.0][3] | [openSUSE 10.3][4]

**Fedora:**

From what I gather, KDE 4.2 is not yet available as an update to Fedora 10.  You&#8217;ll have to enable the testing repos by typing

> `yum --enablerepo=kde-testing,kde-testing-all update`

at the terminal followed by

> `yum groupinstall "KDE (K Desktop Environment)"`

Do note you need to be root to do so.

**Debian Lenny:** Check [this post][5]

**ArchLinux:**

> `>pacman -Syu`

**Warning: This installs KDE 4.2 pkgs alright, however, kdm will not start
  
now. Forums have no solution yet.** 

Thanks to RollMeWay for [the][6] [inputs][7]

Some pics:

[<img src="https://i2.wp.com/farm4.static.flickr.com/3454/3242040790_e85b436280.jpg?resize=500%2C313" alt="KDE 4.2 show all windows" width="500" height="313" data-recalc-dims="1" />][8]

[<img src="https://i2.wp.com/farm4.static.flickr.com/3260/3241207261_7ea9753114.jpg?resize=500%2C313" alt="kde 4.2 cube" width="500" height="313" data-recalc-dims="1" />][9]

[<img src="https://i0.wp.com/farm4.static.flickr.com/3489/3241206137_71e738408f.jpg?resize=500%2C313" alt="KDE 4.2 grouping" width="500" height="313" data-recalc-dims="1" />][10]

[<img src="https://i2.wp.com/farm4.static.flickr.com/3308/3241205429_fd2b87786b.jpg?resize=500%2C313" alt="KDE 4.2" width="500" height="313" data-recalc-dims="1" />][11]

**WARNING: While Upgrading to KDE 4.2 on Sabayon, wireless will be broken. This isn&#8217;t KDE 4.2&#8217;s fault, I&#8217;m inclined to say its because of PolicyKit since PolicyKit was installed as I installed KDE4.2 and I know PolicyKit can be a \_real\_ pain.
  
** 

Update: The wireless breaking is a result of Network. Here&#8217;s a post on getting this fixed.

Update: As mentioned by lythandrel, changed removed references to sudo

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/02/01/upgrading-to-kde-42-in-your-favorite-linux-distro/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-674" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/02/01/upgrading-to-kde-42-in-your-favorite-linux-distro/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-674" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/02/01/upgrading-to-kde-42-in-your-favorite-linux-distro/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-674" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/02/01/upgrading-to-kde-42-in-your-favorite-linux-distro/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/02/01/upgrading-to-kde-42-in-your-favorite-linux-distro/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://sathyasays.com/2009/01/28/drum-roll-please-kde-42-is-released/
 [2]: http://download.opensuse.org/repositories/KDE:/KDE4:/Factory:/Desktop/openSUSE_11.1/KDE4-DEFAULT.ymp
 [3]: http://download.opensuse.org/repositories/KDE:/KDE4:/Factory:/Desktop/openSUSE_11.0/KDE4-DEFAULT.ymp
 [4]: http://download.opensuse.org/repositories/KDE:/KDE4:/Factory:/Desktop/openSUSE_10.3/KDE4-DEFAULT.ymp
 [5]: http://linuxsaga.com/guide/kde-42-in-debian-testing-lenny
 [6]: http://sathyasays.com/2009/02/01/upgrading-to-kde-42-in-your-favorite-linux-distro/comment-page-1/#comment-24047
 [7]: http://sathyasays.com/2009/02/01/upgrading-to-kde-42-in-your-favorite-linux-distro/comment-page-1/#comment-24063
 [8]: http://www.flickr.com/photos/sathyabhat/3242040790/
 [9]: http://www.flickr.com/photos/sathyabhat/3241207261/
 [10]: http://www.flickr.com/photos/sathyabhat/3241206137/
 [11]: http://www.flickr.com/photos/sathyabhat/3241205429/
---
title: NetworkManager 0.70 breaks wireless for Intel 3945 users on Sabayon, here’s how to fix it
author: Sathya
type: post
date: 2009-02-02T04:57:15+00:00
url: /2009/02/02/networkmanager-070-breaks-wireless-for-intel-3945-users-on-sabayon-heres-how-to-fix-it/
categories:
  - "Tips &amp; How-To's"
tags:
  - DE
  - forums
  - Gentoo
  - install
  - intel
  - KDE
  - KDE 4.2
  - net
  - NetworkManager
  - os
  - package manager
  - repo
  - repos
  - rm
  - root
  - Sabayon
  - switch
  - switching
  - sync
  - update
  - upgrade
  - user
  - WiFi
  - Wireless
  - X

---
Well like I mentioned in my previous post, as I upgraded my system to KDE 4.2, NetworkManager 0.70 was also pushed in the update, and that broke my wireless. NetworkManager didn&#8217;t detect \*any\* of my network devices(yup, not even the ethernet port). A small post on Sabayon forums and I got the confirmation that I wasn&#8217;t the only one facing this, and the only way (atleast for now) is to downgrade to NetworkManager 0.6.6-r1.

So incase you aren&#8217;t able to connect via wireless, fire up your package manager and downgrade to NetworkManager 0.6.6-r1.

In Sabayon, you can do so by first switching to root.

> `su root`

Next install NetworkManager 6.6-r1
  
<bletockquote>`equo install networkmanager-0.6.6-r1`

In case this version is not present in Sabayon repos (like for me) emerge it from Gentoo sources.
  
Here&#8217;s how. Type

> `emerge --sync && layman -S`

and followed by

> `emerge =net-misc/networkmanager-0.6.6-r1`

That should bring up wireless. Will post if any update fixes this.
  
Thanks to wolfden from Sabayon forums for helping me out with this
  
</bletockquote>
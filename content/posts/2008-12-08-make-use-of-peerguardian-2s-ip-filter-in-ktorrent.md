---
title: Make Use of PeerGuardian 2’s IP Filter in KTorrent
author: Sathya
type: post
date: 2008-12-08T06:16:31+00:00
url: /2008/12/08/make-use-of-peerguardian-2s-ip-filter-in-ktorrent/
categories:
  - "Tips & How-To's"
tags:

  - linux
  - tutorials
  
---
PeerGuardian 2, is an awesome IP filtering software. Though its FOSS, it there isn't a Linux port of it yet. But don't worry, if you're using KTorrent, you can make use of PeerGuardian's filters.  Let me show how you can do so.

<!--more-->

Launch KTorrent. Click on On Settings -> Configure KTorrent . Click on Plugins and ensure that IP FIlter is checked

![Ktorrent settings][1]

Now Click on Apply. Next on the sidebar, scroll down and click on IP Filter. Click on the checkbox next to "Use PeerGuardian Filter". Next just click on Download/Convert. It might take a minute or two for the list to be loaded and converted to a format KTorrent can understand.

![IP-Filter][2]

Next Click on Apply and OK. There you go, you're done. KTorrent now will make use of PeerGuardian's filters.

 [1]: https://farm4.static.flickr.com/3162/3091279823_ccff6b30cd_m.jpg
 [2]: https://farm4.static.flickr.com/3235/3091279829_fbca833b4e_m.jpg

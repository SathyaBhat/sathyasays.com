---
title: If Amarok 2.0 doesn’t add any songs to your playlist or collection…..
author: Sathya
type: post
date: 2009-01-07T01:30:01+00:00
url: /2009/01/07/if-amarok-20-doesnt-add-any-songs-to-your-playlist-or-collection/
categories:
  - "Tips &amp; How-To's"
tags:
  - Amarok
  - Amarok 2
  - install
  - KDE
  - KDE4
  - music
  - MySQL
  - mysql-client
  - "tips-and-howto's"
  - tutorials
  - X
  - xp

---
Here&#8217;s a short tip: If Amarok 2.0 doesn&#8217;t add any songs to your playlist or collection, or the collection scan is getting hung at up 47% or 79% try installing mysql. Since Amarok 2 now makes use of mysql as its backend, it expects mysql to be installed(nope, mysql-client won&#8217;t do either). As a result, after scanning, it cannot add the songs to the collection database and the process just stops.
  
Just install mysql, and you should be rocking to music on Amarok again
---
title: 'Amarok 2.1 is out & Installing Amarok 2.1 on Ubuntu 9.04 Jaunty'
author: Sathya
type: post
date: 2009-06-06T22:07:31+00:00
url: /2009/06/07/amarok-21-is-out-installing-amarok-21-on-ubuntu-904-jaunty/
categories:
  - Reviews
tags:
  - Amarok
  - Amarok 2
  - Apple
  - Arch
  - file
  - forums
  - GNOME
  - Jaunty
  - KDE
  - KDE 4.2
  - kubuntu
  - Launchpad
  - linux
  - open source
  - plasma
  - software
  - SUSE
  - synaptic
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - Ubuntu
---
I was catching up on some feeds yesterday, and this piece of news caught my eye -[Amarok 2.1 released][1]{#aptureLink_chgCx0N0sk}. Being a long time Amarok fan ( heck Amarok itself was catalyst to make me use my SUSE 10.0 use full) time - I read the article with great interest.

Amarok 2 users would know that Amarok 2 series is a shadow of its old Amarok 1.4("Amarok Classic" self) - and quite a few people still prefer Amarok classic to Amarok 2 - primararily because of Amarok's missing support for visualizations, equalizer amongst others. I don't use equalizers - and as for visualization - well don't use that either.

<!--more-->

Coming back to the point - Amarok 2.0 release was somewhat like a KDE 4.0 release - more of a framework release, basic building blocks in place, but just about. I terribly missed queuing support, and promptly stopped using Amarok (and on a different note, switched to Gnome - Rhythmbox is sweet!).

Amarok 2.1 brings in a lot of improvements - and the most obvious one is the improvements to the playlist and main play window area. With Amarok 2.0 - the playlist area was a bit of a hit and a miss the lyrics, Wikipedia info was there but wasn't obvious, you had to "Add the plasma" and once you added multiple plasma("applets") you had no idea how many were there without "zooming out" and overlooking it. And with the zoom effect not at its  slickest best it was a big chore.

Amarok 2.1 fixes this by adding buttons which bring up the respective applets making it easy to remove the exisitng applets, add new ones or simply re-arrange them.

[<img class="aligncenter size-medium wp-image-744" title="amarok-21" src="https://i.sathyabh.at/ss/2009/06/amarok-21-300x187.png" alt="amarok-21"   srcset="https://i.sathyabh.at/ss/2009/06/amarok-21-300x187.png 300w, https://i.sathyabh.at/ss/2009/06/amarok-21-1024x640.png 1024w, https://i.sathyabh.at/ss/2009/06/amarok-21.png 1280w" sizes="(max-width: 300px) 100vw, 300px" />][2]Another nice feature introduced is "bookmarking" - any track with a length greater than 10minutes and Amarok will save the last listened position, so when you return to playing the track, it resumes from the last bookmarked place. There are other improvements too - only I couldn't figure it because the damned player wouldn't play anything :|

<del datetime="2009-06-13T17:04:43+00:00">I've put my query in Ubuntu forums over <a id="aptureLink_QNbmnzqO6M" href="https://ubuntuforums.org/showthread.php?t=1180175">here</a> - my problem is that Amarok just refuses to play any local files. If any of my readers can help me figure this out, it'll be great, just drop a comment.</del>

Edit: Fixed the problem .

As for installing Amarok, its straightforward, Goto System -> Administration -> Software Sources.

Click on third party sources, click on Add, enter the below line.
  
`deb https://ppa.launchpad.net/kubuntu-ppa/backports/ubuntu jaunty main`
  
Save, update. Launch Synaptic, search for amarok and mark for install.
  
That's it, Amarok 2.1 is ready to rock. Were you able to get Amarok successful run on your system ? Do drop a comment.

 [1]: https://amarok.kde.org/en/releases/2.1
 [2]: https://i.sathyabh.at/ss/2009/06/amarok-21.png

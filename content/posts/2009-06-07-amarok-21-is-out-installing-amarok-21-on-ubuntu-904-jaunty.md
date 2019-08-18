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
  - cat
  - DE
  - file
  - forums
  - GNOME
  - hassles
  - IM
  - install
  - Jaunty
  - KDE
  - KDE 4.2
  - kubuntu
  - Launchpad
  - linux
  - move
  - net
  - New
  - open source
  - os
  - plasma
  - read
  - software
  - support
  - SUSE
  - switch
  - synaptic
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - Ubuntu 9.04
  - update
  - user
  - X

---
I was catching up on some feeds yesterday, and this piece of news caught my eye &#8211;[Amarok 2.1 released][1]{#aptureLink_chgCx0N0sk}. Being a long time Amarok fan ( heck Amarok itself was catalyst to make me use my SUSE 10.0 use full) time &#8211; I read the article with great interest.

Amarok 2 users would know that Amarok 2 series is a shadow of its old Amarok 1.4(&#8220;Amarok Classic&#8221; self) &#8211; and quite a few people still prefer Amarok classic to Amarok 2 &#8211; primararily because of Amarok&#8217;s missing support for visualizations, equalizer amongst others. I don&#8217;t use equalizers &#8211; and as for visualization &#8211; well don&#8217;t use that either.

<!--more-->

Coming back to the point &#8211; Amarok 2.0 release was somewhat like a KDE 4.0 release &#8211; more of a framework release, basic building blocks in place, but just about. I terribly missed queuing support, and promptly stopped using Amarok (and on a different note, switched to Gnome &#8211; Rhythmbox is sweet!).

Amarok 2.1 brings in a lot of improvements &#8211; and the most obvious one is the improvements to the playlist and main play window area. With Amarok 2.0 &#8211; the playlist area was a bit of a hit and a miss the lyrics, Wikipedia info was there but wasn&#8217;t obvious, you had to &#8220;Add the plasma&#8221; and once you added multiple plasma(&#8220;applets&#8221;) you had no idea how many were there without &#8220;zooming out&#8221; and overlooking it. And with the zoom effect not at its  slickest best it was a big chore.

Amarok 2.1 fixes this by adding buttons which bring up the respective applets making it easy to remove the exisitng applets, add new ones or simply re-arrange them.

[<img data-attachment-id="744" data-permalink="https://sathyasays.com/2009/06/07/amarok-21-is-out-installing-amarok-21-on-ubuntu-904-jaunty/amarok-21/" data-orig-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/06/amarok-21.png?fit=1280%2C800&ssl=1" data-orig-size="1280,800" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="amarok-21" data-image-description="" data-medium-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/06/amarok-21.png?fit=300%2C187&ssl=1" data-large-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/06/amarok-21.png?fit=740%2C463&ssl=1" class="aligncenter size-medium wp-image-744" title="amarok-21" src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/06/amarok-21-300x187.png?resize=300%2C187" alt="amarok-21" width="300" height="187" srcset="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/06/amarok-21.png?resize=300%2C187&ssl=1 300w, https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/06/amarok-21.png?resize=1024%2C640&ssl=1 1024w, https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/06/amarok-21.png?w=1280&ssl=1 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][2]Another nice feature introduced is &#8220;bookmarking&#8221; &#8211; any track with a length greater than 10minutes and Amarok will save the last listened position, so when you return to playing the track, it resumes from the last bookmarked place. There are other improvements too &#8211; only I couldn&#8217;t figure it because the damned player wouldn&#8217;t play anything :|

<del datetime="2009-06-13T17:04:43+00:00">I&#8217;ve put my query in Ubuntu forums over <a id="aptureLink_QNbmnzqO6M" href="http://ubuntuforums.org/showthread.php?t=1180175">here</a> &#8211; my problem is that Amarok just refuses to play any local files. If any of my readers can help me figure this out, it&#8217;ll be great, just drop a comment.</del>

Edit: Fixed the problem .

As for installing Amarok, its straightforward, Goto System -> Administration -> Software Sources.

Click on third party sources, click on Add, enter the below line.
  
`deb http://ppa.launchpad.net/kubuntu-ppa/backports/ubuntu jaunty main`
  
Save, update. Launch Synaptic, search for amarok and mark for install.
  
That&#8217;s it, Amarok 2.1 is ready to rock. Were you able to get Amarok successful run on your system ? Do drop a comment.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/06/07/amarok-21-is-out-installing-amarok-21-on-ubuntu-904-jaunty/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-743" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/06/07/amarok-21-is-out-installing-amarok-21-on-ubuntu-904-jaunty/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-743" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/06/07/amarok-21-is-out-installing-amarok-21-on-ubuntu-904-jaunty/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-743" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/06/07/amarok-21-is-out-installing-amarok-21-on-ubuntu-904-jaunty/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/06/07/amarok-21-is-out-installing-amarok-21-on-ubuntu-904-jaunty/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://amarok.kde.org/en/releases/2.1
 [2]: https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/06/amarok-21.png
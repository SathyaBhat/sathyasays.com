---
title: '[How-to] Fix the Buggy Intel Driver in Jaunty'
author: Bharath
type: post
date: 2009-06-12T15:49:40+00:00
url: /2009/06/12/how-to-fix-the-buggy-intel-driver-in-jaunty/
categories:
  - "Tips &amp; How-To's"
tags:
  - codecs
  - commands
  - compiz
  - compiz fusion
  - DE
  - Desktop
  - driver
  - drivers
  - eye-candy
  - find
  - how-tos
  - install
  - intel
  - intrepid
  - Jaunty
  - linux
  - music
  - open source
  - os
  - tar
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - videos
  - VLC
  - X
  - xorg

---
So this is a short post on one pestering problem. If youre using Jaunty and find this problem then use the link that follows.

When i installed Jaunty i had problems (as usual). One of them was this. First off, videos wont play in any video player. Codecs are in place, no doubt. But the player would go crashing down. Even vlc, which uses a seperate set of codecs fails :(

Then, desktop effects wont enable. No matter what. An irritating piece of  thing.

But it was so queer that when rhythmbox (may be others too; i dont know) starts playing (not just open but playing) videos work! But i dont think video players should be dependent on music players.

So what worked for me was I rolledback to intrepid&#8217;s version (2.4) version of xserver-xorg-video-intel. Now no problems videos play and compiz is enabled.

[Click here][1] to find out how to revert to the 2.4 version.

Hope this helps.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/06/12/how-to-fix-the-buggy-intel-driver-in-jaunty/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-748" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/06/12/how-to-fix-the-buggy-intel-driver-in-jaunty/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-748" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/06/12/how-to-fix-the-buggy-intel-driver-in-jaunty/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-748" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/06/12/how-to-fix-the-buggy-intel-driver-in-jaunty/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/06/12/how-to-fix-the-buggy-intel-driver-in-jaunty/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: https://wiki.ubuntu.com/ReinhardTartler/X/RevertingIntelDriverTo2.4
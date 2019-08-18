---
title: NVIDIA Adds PureVideo support to its Linux Drivers
author: Sathya
type: post
date: 2008-11-16T17:32:47+00:00
url: /2008/11/16/nvidia-adds-purevideo-support-to-its-linux-drivers/
categories:
  - News
tags:
  - beta
  - DE
  - driver
  - drivers
  - free
  - install
  - linux
  - net
  - New
  - notes
  - NVIDIA
  - Purevideo
  - read
  - support
  - ux
  - X

---
NVIDIA released their <a href="http://www.nvnews.net/vbulletin/showthread.php?t=123072" target="_blank">new set of beta drivers</a> yesterday, with a version 180.04. While going through the release notes, I found this line very interesting.

> Added initial support for PureVideo-like features on Linux via the new VDPAU AP.

Now I don&#8217;t know what exactly they mean by &#8220;initial support&#8221; but nonetheless its a pretty good that they (finally) decided to add PureVideo support.

In case you&#8217;re wondering what <a rel="wikipedia" href="http://en.wikipedia.org/wiki/Purevideo">PureVideo</a>is all about, PureVideo is a decoder which offloads decoding of MPEG2 & H.264 streams over to GPU, leaving the CPU free for other tasks. Read up on PureVideo more on the wiki.

Links to the drivers: [x86][1] / [x86-64][2]

Here&#8217;s my [how-to on installing the drivers][3].

Do note that the drivers are still BETA.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/11/16/nvidia-adds-purevideo-support-to-its-linux-drivers/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-564" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/11/16/nvidia-adds-purevideo-support-to-its-linux-drivers/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-564" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/11/16/nvidia-adds-purevideo-support-to-its-linux-drivers/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-564" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/11/16/nvidia-adds-purevideo-support-to-its-linux-drivers/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/11/16/nvidia-adds-purevideo-support-to-its-linux-drivers/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://www.nvidia.com/object/linux_display_ia32_180.06.html
 [2]: http://www.nvidia.com/object/linux_display_amd64_180.06.html
 [3]: http://sathyasays.com/2007/12/15/compiz-fusion-on-opensuse-103-and-nvidia-cards/
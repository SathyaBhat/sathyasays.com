---
title: NVIDIA Quietly Releases 171.05 Drivers
author: Sathya
type: post
date: 2008-02-02T17:33:13+00:00
url: /2008/02/02/nvidia-quietly-releases-17105-drivers/
categories:
  - News
tags:
  - bin
  - cat
  - DE
  - driver
  - drivers
  - install
  - linux
  - mount
  - New
  - NVIDIA
  - os
  - performance
  - read
  - rm
  - support
  - update
  - ux
  - X

---
Last night NVIDIA quietly uploaded a new Linux display driver to their FTP server. This new driver is tagged 171.05, while the latest public driver has been 169.09. Having already three releases in the 169.xx series, this is a moderate update to 171.xx, but according to NVIDIA it&#8217;s not for everyone. There is no official change-log that NVIDIA has published for the 171.05 driver, and the change-log that ships with the driver hasn&#8217;t been updated (whether it be intentional or not). The only word that has come out of the NVIDIA camp on this new driver is from Christian Zander and he has said that this driver is only intended for use with the Tesla S870 GPU Computing Systems. The legacy NVIDIA Linux drivers have also been updated this week.
  
NVIDIA&#8217;s Tesla S870 GPU computing system is designed for high-performance computing (HPC) environments and has a total of 6GB of dedicated video memory, which is shared by the four 128 processing core GPUs that make up the S870, and is all housed inside a 1U rackmount chassis. NVIDIA&#8217;s Tesla was originally introduced in June of last year, but the 171.05 driver is the first Linux release to support the Tesla S870.
  
So far we noticed one change with the 171.05 driver and that is the introduction of a new NVIDIA utility, nvidia-smi. This utility is for the NVIDIA System Management Interface and provides system-state and diagnostic information. Nvidia-smi will dump this system information either as ASCII text or into an XML log. In addition to the output format, other arguments include _-l_ for creating an infinite loop of nvidia-smi, _-t_ for toggling the LED state, and _-i_ for probing every specified number of seconds. According to the man page and the _&#8211;help_ output, nvidia-smi is only designed for the NVIDIA Tesla S870. However, nvidia-smi had run with a GeForce 8 graphics card installed but with little information. Likewise, the 171.05 driver during our initial tests had worked just fine when using it in a non-Tesla environment.
  
You can try out this driver by heading on over to the <a href="ftp://download.nvidia.com/XFree86/Linux-x86/171.05/" target="_blank">NVIDIA FTP server</a>.

Source: [Phoronix][1]

Technorati Tags: <a href="http://technorati.com/tag/Linux" class="performancingtags" rel="tag">Linux</a>, <a href="http://technorati.com/tag/NVIDIA" class="performancingtags" rel="tag">NVIDIA</a>, <a href="http://technorati.com/tag/Drivers" class="performancingtags" rel="tag">Drivers</a>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/02/02/nvidia-quietly-releases-17105-drivers/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-252" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/02/02/nvidia-quietly-releases-17105-drivers/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-252" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/02/02/nvidia-quietly-releases-17105-drivers/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-252" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/02/02/nvidia-quietly-releases-17105-drivers/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/02/02/nvidia-quietly-releases-17105-drivers/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://www.phoronix.com/scan.php?page=article&item=987&num=1
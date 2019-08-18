---
title: Mounting and Burning .iso, .mdf, .nrg(Nero) files and CD Images in Linux in 1-click
author: Sathya
type: post
date: 2008-11-11T04:30:47+00:00
url: /2008/11/11/mounting-and-burning-iso-mdf-nrgnero-files-and-cd-images-in-linux-in-1-click/
categories:
  - Reviews
tags:
  - bin
  - Brasero
  - cat
  - commands
  - community
  - DE
  - Debian
  - file
  - Home
  - IM
  - images
  - install
  - iso
  - linux
  - mdf
  - mds
  - mount
  - mounting
  - mounting images
  - mounting iso images
  - Nautilus
  - nrg
  - open source
  - openSuSE
  - os
  - repo
  - repos
  - repositories
  - show
  - software
  - SUSE
  - "tips-and-howto's"
  - Ubuntu
  - Unity
  - user
  - ux
  - X
  - YaST

---
A while ago, I&#8217;d written a post on [howto mount CD images][1], such as .iso, .mdf files etc via the command prompt using the mount command. In the post, among the comments, Sumeet had asked if there was a way to do all of this without having to type lengthy commands. Well yes there is! And it can&#8217;t get simpler than this!

<p style="text-align: center;">
  <!--more-->Furious ISO Mount Tool is a an amazing little application, taking only about 256KB, and gives you a neat little interface to mount all your iso, mdf(ie, made by Alcohol 120), nrg(created using Nero) images using 1 click!
  
  <br /> <a href="http://www.flickr.com/photos/sathyabhat/3019351633/"><img class="aligncenter" src="https://i1.wp.com/farm4.static.flickr.com/3005/3019351633_6396ab88db_m.jpg?w=740" alt="Furious ISO Mount Tool" data-recalc-dims="1" /></a>
</p>

As the above pic shows, the interface is simplistic. To mount an image, just hit the browse button, choose the image file, and hit the mount button! The image will be mounted in your home directory. Furious ISO Mount tool can also launch Brasero or Nautilus and burn the image file, and can also calculate the SHA/HD5 hash, to check that the ISO is not corrupted.
  
This app is a must-install, highly recommended app! Go install it!
  
openSUSE users, can get it from YaST, provided you have PackMan repo configured. If not, add it by clicking on YaST -> Software Repositories -> Click on ADd and Choose Community Repositories. From here select PackMan (and optionally, others too ;-) ) repositories

Debian/Ubuntu users can grab the installer from here:
  
For [32-bit(x86)][2] / For [64-bit (amd64)][3]

You can [grab the sources][4] and [recompile it as well][5].

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/11/11/mounting-and-burning-iso-mdf-nrgnero-files-and-cd-images-in-linux-in-1-click/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-562" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/11/11/mounting-and-burning-iso-mdf-nrgnero-files-and-cd-images-in-linux-in-1-click/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-562" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/11/11/mounting-and-burning-iso-mdf-nrgnero-files-and-cd-images-in-linux-in-1-click/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-562" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/11/11/mounting-and-burning-iso-mdf-nrgnero-files-and-cd-images-in-linux-in-1-click/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/11/11/mounting-and-burning-iso-mdf-nrgnero-files-and-cd-images-in-linux-in-1-click/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://sathyasays.com/2007/12/15/mounting-iso-and-mdsmdf-files-in-linux/
 [2]: http://www.marcus-furius.com/files/FuriusIsoMount/furiusisomount_0.9.0.2-1_i386.deb
 [3]: http://www.marcus-furius.com/files/FuriusIsoMount/furiusisomount_0.9.0.2-1_amd64.deb
 [4]: http://www.marcus-furius.com/files/FuriusIsoMount/furiusisomount-0.9.0.2.tar.gz
 [5]: http://sathyasays.com/2008/07/24/how-to-compile-a-program-from-source-code-installing-from-source/
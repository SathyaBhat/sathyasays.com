---
title: '[How To] Solution for sudo: must be setuid root problem'
author: Bharath
type: post
date: 2008-10-10T17:05:07+00:00
url: /2008/10/10/how-to-solution-for-sudo-must-be-setuid-root-problem/
categories:
  - "Tips &amp; How-To's"
tags:
  - bin
  - cat
  - chm
  - commands
  - DE
  - dl
  - install
  - linux
  - mount
  - os
  - partition
  - rm
  - root
  - setuid
  - setuid root
  - sudo
  - suid
  - terminal
  - "tips-and-howto's"
  - tutorials
  - X

---
I had encountered this problem on [sudo][1]/[gksu][2] not working few months earlier.

Whenever I had to open an application with gksu it did not open at all !  I was wondering what did i do. I dint know whether  i meddled with something or is it any other configuration that created the problem.

If I type sudo in terminal i get &#8220;sudo: must be setuid root&#8221;

This is how I went about fixing it:-

  1. Open terminal and enter as root i.e. type &#8216;su&#8217; and then the root password (Please be careful while being the root). Alternatively, you can also use ur OS&#8217;s live CD to mount the root partition (the partition where you have installed your OS)
  2. Next, type `chmod 4755 /usr/bin/sudo` If the command perfectly happens then as far I am able to tell sudo and gksu should work correctly.

If anyone of you are still having problems regarding this issue please post it in comments

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/10/10/how-to-solution-for-sudo-must-be-setuid-root-problem/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-451" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/10/10/how-to-solution-for-sudo-must-be-setuid-root-problem/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-451" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/10/10/how-to-solution-for-sudo-must-be-setuid-root-problem/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-451" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/10/10/how-to-solution-for-sudo-must-be-setuid-root-problem/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/10/10/how-to-solution-for-sudo-must-be-setuid-root-problem/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://www.tech-faq.com/sudo.shtml
 [2]: http://linux.about.com/cs/linux101/g/gksu.htm
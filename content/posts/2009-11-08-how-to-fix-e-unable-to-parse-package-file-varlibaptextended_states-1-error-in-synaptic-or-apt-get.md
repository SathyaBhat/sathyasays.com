---
title: '[How-to] Fix “E: Unable to parse package file /var/lib/apt/extended_states (1)”  error in Synaptic or apt-get'
author: Bharath
type: post
date: 2009-11-08T11:41:22+00:00
url: /2009/11/08/how-to-fix-e-unable-to-parse-package-file-varlibaptextended_states-1-error-in-synaptic-or-apt-get/
categories:
  - "Tips &amp; How-To's"
tags:
  - apt-get
  - cloeses
  - DE
  - 'E: Unable to parse package file /var/lib/apt/extended_states (1)'
  - exe
  - exits
  - file
  - install
  - os
  - read
  - repo
  - rm
  - sudo
  - synaptic
  - terminal
  - unable
  - X

---
This is just a quick tip. If you are getting this error message in Synaptic:

> E: Unable to parse package file /var/lib/apt/extended_states (1)
  
> E: _cache->open() failed, please report

or this error in apt-get in command line:

> Reading package lists&#8230; Done
  
> Building dependency tree
  
> Reading state information&#8230; Error!
  
> E: Unable to parse package file /var/lib/apt/extended_states (1)

and both just fail to open or install, then just execute this in command line (terminal):

> sudo mv /var/lib/apt/extended\_states /var/lib/apt/extended\_states_tmp

You are done. Thanks to [this][1] post

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/11/08/how-to-fix-e-unable-to-parse-package-file-varlibaptextended_states-1-error-in-synaptic-or-apt-get/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-762" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/11/08/how-to-fix-e-unable-to-parse-package-file-varlibaptextended_states-1-error-in-synaptic-or-apt-get/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-762" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/11/08/how-to-fix-e-unable-to-parse-package-file-varlibaptextended_states-1-error-in-synaptic-or-apt-get/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-762" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/11/08/how-to-fix-e-unable-to-parse-package-file-varlibaptextended_states-1-error-in-synaptic-or-apt-get/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/11/08/how-to-fix-e-unable-to-parse-package-file-varlibaptextended_states-1-error-in-synaptic-or-apt-get/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://ubuntuforums.org/showthread.php?t=724916
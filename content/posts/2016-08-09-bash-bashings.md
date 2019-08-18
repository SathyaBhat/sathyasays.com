---
title: Bash bashings..
author: Sathya
type: post
date: 2016-08-09T18:37:28+00:00
url: /2016/08/09/bash-bashings/
categories:
  - "Tips &amp; How-To's"
tags:
  - bash
  - linux
  - popd
  - pushd

---
Since <a href="http://sathyabh.at/2016/07/12/in-with-the-new-job/" target="_blank">my new job</a> involves lot more of Linux, shell scripting bash and automation, I&#8217;ve been trying to brush up my Linux skills. Ran into this &#8220;problem&#8221; today where there&#8217;s an init script which handles unicorn start/stop/reload and we were debugging some kinks around this. The init script had a chain of cd to the directory and the unicorn invoke script. Was trying to figure out why unicorn wasn&#8217;t starting up, till I read a bit more and dropped to using echo to understand what&#8217;s happening



This should give an idea. After experimenting with eval, pushd/popd, bash subroutines and some more things, both the Tech Architect and me did a facepalm when we realized&#8230; the script does a cd at start we really didn&#8217;t need that chaining.

&nbsp;

(inb4  you-so-n00b etc etc)

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2016/08/09/bash-bashings/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1451" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2016/08/09/bash-bashings/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1451" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2016/08/09/bash-bashings/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1451" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2016/08/09/bash-bashings/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2016/08/09/bash-bashings/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
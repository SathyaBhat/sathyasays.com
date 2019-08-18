---
title: '[How to] Setting up Frontech Tv Tuner in Linux'
author: Bharath
type: post
date: 2008-10-22T04:30:22+00:00
url: /2008/10/22/how-to-set-up-frontech-tv-tuner-in-linux/
categories:
  - "Tips &amp; How-To's"
tags:
  - AA
  - blog
  - commands
  - DE
  - driver
  - Fedora
  - Frontech
  - install
  - internet
  - KDE TV
  - linux
  - LV
  - net
  - personal
  - read
  - RIA
  - rm
  - "tips-and-howto's"
  - Tuner
  - tutorials
  - TV
  - TV TIme
  - user
  - ux
  - X

---
Continue I am personally a Frontech tv tuner user. I dont currently use it now but i was using in the past. I faced hell a lot of problems to get it working. It was sheer luck that i ran into the info [here][1] which saved me!!!! Thanks to Mann.

Here&#8217;s an excerpt from it

> 13/06/07- I cannot install my TV tuner card in fedora (this problem is irrelevant to my project, but i want it to be solved)
> 
> Causes:
  
> Its a cheap card and manufacture didn&#8217;t provide the sufficient information on its EEPROM. So fedora cannot recognize it automatically and hence driver is not loaded.

Solutions tried

  1. From internet and using the commands dmesg and lspci -v, i was able to figure out that it is <span style="#990000;">saa7130</span> chip based card.
  2. The thing to do here is to figure out the card type and tuner number by yourself and load the modules But in fedora there are 108 cards with different tuner number number. The last tuner number I tried was 71 and the list was more than 71 I think. So I sticked to card number 3 and tried different variations of tuner number from 1 to 71.

Continue Reading over at <a href="http://mann-linuxproject.blogspot.com/2007/06/problem3.html" target="_blank">Mann&#8217;s blog</a>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/10/22/how-to-set-up-frontech-tv-tuner-in-linux/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-492" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/10/22/how-to-set-up-frontech-tv-tuner-in-linux/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-492" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/10/22/how-to-set-up-frontech-tv-tuner-in-linux/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-492" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/10/22/how-to-set-up-frontech-tv-tuner-in-linux/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/10/22/how-to-set-up-frontech-tv-tuner-in-linux/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://mann-linuxproject.blogspot.com/2007/06/problem3.html
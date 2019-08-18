---
title: Fixing Sabayon 4 dropping to console/terminal when pressing the Windows Key
author: Sathya
type: post
date: 2009-01-16T02:02:44+00:00
url: /2009/01/16/fixing-sabayon-4-dropping-to-consoleterminal-when-pressing-the-windows-key/
categories:
  - "Tips &amp; How-To's"
tags:
  - bin
  - boot
  - console
  - DE
  - IM
  - keyboard
  - Meta
  - move
  - os
  - review
  - rm
  - root
  - Sabayon
  - Sabayon 4
  - Super
  - switch
  - switching
  - terminal
  - "tips-and-howto's"
  - update
  - windows
  - X

---
I&#8217;ve been trying out Sabayon 4 since the past weeks, and its been really great (will post a review soon). The one really irritating thing though, is on hitting the Windows(&#8220;Super&#8221;) key on the keyboard would result in Sabayon 4 switching VT&#8217;s. Now if you&#8217;ve no idea what VT&#8217;s are&#8230;. well that I would post some other time, basically you&#8217;d drop to a console prompt.

Anyways to remove this binding, open the Terminal, switch to root by typing `su root`

Now, type `rc-update del keymaps default; rc-update add keymaps boot` hit Enter, and reboot.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/01/16/fixing-sabayon-4-dropping-to-consoleterminal-when-pressing-the-windows-key/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-657" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/01/16/fixing-sabayon-4-dropping-to-consoleterminal-when-pressing-the-windows-key/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-657" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/01/16/fixing-sabayon-4-dropping-to-consoleterminal-when-pressing-the-windows-key/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-657" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/01/16/fixing-sabayon-4-dropping-to-consoleterminal-when-pressing-the-windows-key/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/01/16/fixing-sabayon-4-dropping-to-consoleterminal-when-pressing-the-windows-key/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
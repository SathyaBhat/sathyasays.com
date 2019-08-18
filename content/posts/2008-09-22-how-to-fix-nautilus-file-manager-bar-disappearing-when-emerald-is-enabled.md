---
title: '[How-To] Fix Nautilus File Manager Title Bar(Window Decorator) disappearing when Emerald is enabled'
author: Sathya
type: post
date: 2008-09-21T18:36:25+00:00
url: /2008/09/22/how-to-fix-nautilus-file-manager-bar-disappearing-when-emerald-is-enabled/
categories:
  - "Tips &amp; How-To's"
tags:
  - applications
  - cat
  - DE
  - Emerald
  - file
  - find
  - gconf
  - gtk
  - linux
  - Meta
  - Nautilus
  - open source
  - os
  - Resolution
  - rm
  - Screen
  - Screen Resolution
  - terminal
  - "tips-and-howto's"
  - window-decorator
  - windows
  - X
  - xp

---
Most of the how-to&#8217;s and fixes posted here, are generally my experiences and I post them on how I went about fixing it. This particular how-to was mentioned to me by my very good friend, Bharath, who had this annoying problem of the title bars of every window crashing and disappearing when Emerald is chosen as the decorator.

Generally, I&#8217;d recommend running `gtk-window-decorator --replace` or `metacity --replace` in terminal &#8211; that generally does reinitialize the window decorators. However for Bharath, this particular solution didn&#8217;t help and he kept facing the same problem

<!--more-->

Despite typing the above, the title bars would still keep crashing. After some problem he was able to fix it. This is how he went about it.

 

  1. Open Gconf-editor
  2. Head to Applications -> Nautilus -> Preferences
  3. Modify key &#8220;navigation\_windows\_saved_geometry&#8221; to a resolution, that is lesser than the current screen resolution.

<div>
  Do note that you should ideally do this with none of the Nautilus windows open. Save Gconf editor, and launch Nautilus, the title bars should be back now.
</div>

<div>
  Thanks for the tip, Bharath, I&#8217;m sure many people will find this tip useful.
</div>

<div>
  If you have a tip to share, then please use the Contact Me form and get in touch with me, I will post the tip&#8230;
</div>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/09/22/how-to-fix-nautilus-file-manager-bar-disappearing-when-emerald-is-enabled/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-393" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/09/22/how-to-fix-nautilus-file-manager-bar-disappearing-when-emerald-is-enabled/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-393" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/09/22/how-to-fix-nautilus-file-manager-bar-disappearing-when-emerald-is-enabled/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-393" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/09/22/how-to-fix-nautilus-file-manager-bar-disappearing-when-emerald-is-enabled/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/09/22/how-to-fix-nautilus-file-manager-bar-disappearing-when-emerald-is-enabled/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
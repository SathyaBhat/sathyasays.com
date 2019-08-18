---
title: Making Dolphin the Default File Manager
author: Sathya
type: post
date: 2007-06-18T10:59:02+00:00
url: /2007/06/18/making-dolphin-the-default-file-manager/
categories:
  - News
tags:
  - applications
  - apt-get
  - associations
  - cat
  - DE
  - Dolphin
  - file
  - file associations
  - IM
  - install
  - KDE
  - kmenu
  - Konqueror
  - menu
  - move
  - moving
  - os
  - quotes
  - read
  - X
  - xp

---
Dolphin&#8217;s fast loading times and clean interface made me consider to have a second look at Dolphin. So here&#8217;s a way to make Dolphin the default file manager.

If you haven&#8217;t installed Dolphin yet, install it via apt-get or Adept. More info about that in my [previous post][1].

Then, Click on K Menu -> Run Command and type &#8216;kcontrol&#8217; (without the quotes, of course).

Then Click on KDE Components -> File Associations. Expand the inode section.</p> 

<p style="text-align:center;">
  <img src="https://i0.wp.com/sathyasays.wordpress.com/files/2007/06/dolphin-default.thumbnail.jpg?w=740" alt="dolphin-default.jpg" data-recalc-dims="1" />
</p>

</a>Make Dolphin the first choice, by moving it above Konqueror in the precedence order. This will ensure that Dolphin gets the first priority for opening directories.

To make dolphin the default file manager for the virtual directories kde creates e.g. system:/ then again in the File Associations section of the control centre expand the inode section of Known Types. Under the system_directory mime type, add dolphin to the list of applications(If Dolphin entry is already present, remove it), however instead of choosing dolphin from the kmenu, type the following in to the text box at the top dolphin %u The virtual directories created by kde will then be opened by dolphin as default

Voila! Dolphin is now your default file manager!

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/06/18/making-dolphin-the-default-file-manager/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-23" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/06/18/making-dolphin-the-default-file-manager/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-23" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/06/18/making-dolphin-the-default-file-manager/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-23" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/06/18/making-dolphin-the-default-file-manager/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/06/18/making-dolphin-the-default-file-manager/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
          
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://sathyasays.wordpress.com/2007/06/14/a-look-at-dolphin/
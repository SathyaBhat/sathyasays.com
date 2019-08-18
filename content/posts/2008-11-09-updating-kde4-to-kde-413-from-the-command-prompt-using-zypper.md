---
title: Updating KDE4 to KDE 4.1.3 from the command prompt using zypper
author: Sathya
type: post
date: 2008-11-09T13:28:05+00:00
url: /2008/11/09/updating-kde4-to-kde-413-from-the-command-prompt-using-zypper/
categories:
  - News
tags:
  - cat
  - commands
  - DE
  - Desktop
  - dl
  - download
  - free
  - HAL
  - install
  - internet
  - KDE
  - kde 4.1
  - KDE4
  - KDE4.0
  - net
  - openSuSE
  - os
  - repo
  - repos
  - repositories
  - SUSE
  - update
  - updating
  - upgrade
  - X
  - YaST
  - zypper

---
Couple of days ago, while I was updating the KDE4.0.4 install present on my openSUSE, my Internet conked off(as usual), and I was stuck halfway between the KDE4.0.4 -> KDE 4.1.3 update. So I shutdown my system. Later on while powering it on, this semi-update badly damaged by KDE installation with version incompatibilities and DBUS communication failures &#8211; resulting that my X server wouldn&#8217;t come up, with KDE chosen as the DE. With KDE out, I was trying to figure out how to get it updated, without any GUI tools(generally I rely on YaST2) and then I thought why not try out <a rel="wikipedia" href="http://en.wikipedia.org/wiki/Zypper">zypper</a>

<!--more-->


  
With the man page and #openSUSE at Freenode as reference, I managed to get KDE updated using couple of commands.
  
They were:

> `zypper refresh`

This refreshes the repositories &#8211; this will be needed, if [you&#8217;ve disabled auto-refresh of repositories][1].

Now that the repos are refresh, upgrade the pacakges by typing

>  `zypper up -t package -r <Name/Alias given to the repo><br />
` 

That&#8217;s it. KDE will be updated to the latest version.
  
In case you haven&#8217;t added the repo, add it by typing

> `zypper ar -r http://download.opensuse.org/repositories/KDE:/KDE4:/Factory:/Desktop/openSUSE_Factory -n KDE4_1`

This will add an entry to repositories with the name KDE4_1 that you can use in the above zypper command, next to the -r parameter

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/11/09/updating-kde4-to-kde-413-from-the-command-prompt-using-zypper/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-557" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/11/09/updating-kde4-to-kde-413-from-the-command-prompt-using-zypper/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-557" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/11/09/updating-kde4-to-kde-413-from-the-command-prompt-using-zypper/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-557" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/11/09/updating-kde4-to-kde-413-from-the-command-prompt-using-zypper/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/11/09/updating-kde4-to-kde-413-from-the-command-prompt-using-zypper/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://sathyasays.com/2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11
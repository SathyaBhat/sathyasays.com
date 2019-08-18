---
title: Always display the location bar in Nautilus
author: Sathya
type: post
date: 2010-08-30T04:06:10+00:00
url: /2010/08/30/always-display-the-location-bar-in-nautilus/
topsy_short_url:
  - http://bit.ly/90bWfZ
categories:
  - "Tips &amp; How-To's"
tags:
  - apps
  - cat
  - commands
  - DE
  - distro
  - distros
  - dl
  - File management
  - gconf
  - GNOME
  - IM
  - linux
  - Nautilus
  - New
  - open source
  - os
  - rm
  - show
  - tar
  - terminal
  - tips
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - user
  - X

---
This is a pretty good tip. The default style irritates me to no end. Check out the full post, there are some great tips, especially if you&#8217;re new to Nautilus like me.

> Ever since some distros started their attempt to become more “user-friendly” and gaining the nice looks, some default features got changed.
> 
> In this case, it’s the location bar. Instead of it they got some buttons that shows the location and let you navigate through the directories! So, if you’re using one of these distros and want to pop up the location bar, all you have to do is to hit Ctrl+L. However, if you’re like me and like to have it always there, each time you fire it up, you can[change the default value of it in gconf-editor][1], or alternatively use this following command in the terminal
> 
> `gconftool-2 --set /apps/nautilus/preferences/start_with_location_bar --type bool 1`

via [anxiousnut&#8217;s playground][2]

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2010/08/30/always-display-the-location-bar-in-nautilus/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-904" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2010/08/30/always-display-the-location-bar-in-nautilus/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-904" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2010/08/30/always-display-the-location-bar-in-nautilus/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-904" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2010/08/30/always-display-the-location-bar-in-nautilus/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2010/08/30/always-display-the-location-bar-in-nautilus/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://zappedpoint.wordpress.com/2010/05/14/change-the-default-view-in-nautilus
 [2]: http://anxiousnut.wordpress.com/2010/08/28/nautilus-unpopular-flabbergasting-snippets/
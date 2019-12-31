---
title: Always display the location bar in Nautilus
author: Sathya
type: post
date: 2010-08-30T04:06:10+00:00
url: /2010/08/30/always-display-the-location-bar-in-nautilus/
topsy_short_url:
  - https://bit.ly/90bWfZ
categories:
  - "Tips &amp; How-To's"
tags:
  - apps
  - commands
  - distro
  - dl
  - File management
  - gconf
  - GNOME
  - linux
  - Nautilus
  - open source
  - show
  - terminal
  - tips
  - "tips-and-howto's"
  - tutorials
  - Ubuntu

---
This is a pretty good tip. The default style irritates me to no end. Check out the full post, there are some great tips, especially if you're new to Nautilus like me.

> Ever since some distros started their attempt to become more “user-friendly” and gaining the nice looks, some default features got changed.
> 
> In this case, it’s the location bar. Instead of it they got some buttons that shows the location and let you navigate through the directories! So, if you’re using one of these distros and want to pop up the location bar, all you have to do is to hit Ctrl+L. However, if you’re like me and like to have it always there, each time you fire it up, you can[change the default value of it in gconf-editor][1], or alternatively use this following command in the terminal
> 
> `gconftool-2 --set /apps/nautilus/preferences/start_with_location_bar --type bool 1`

via [anxiousnut's playground][2]

 [1]: https://zappedpoint.wordpress.com/2010/05/14/change-the-default-view-in-nautilus
 [2]: https://anxiousnut.wordpress.com/2010/08/28/nautilus-unpopular-flabbergasting-snippets/

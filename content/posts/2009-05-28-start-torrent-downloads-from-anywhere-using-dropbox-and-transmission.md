---
title: Start torrent downloads from anywhere using Dropbox and Transmission
author: Sathya
type: post
date: 2009-05-28T01:20:08+00:00
url: /2009/05/28/start-torrent-downloads-from-anywhere-using-dropbox-and-transmission/
categories:
  - "Tips & How-To's"
tags:
  - accessible
  - chm
  - DropBox
  - file
  - how-tos
  - show
  - sync
  - "tips-and-howto's"
  - torrents
  - transmission
  - tutorials
  - web

---
I've been using [Dropbox][1] pretty extensively ever since its private beta days and just love its simplicity and ease with which I can keep all my files in sync across multiple computers. Even more awesome is its simple web interface - just upload a file and boom, the file you uploaded gets sync'd across all your computers. This coupled with [Transmission][2]{#aptureLink_qW0FfjT1X1}&#8216;s ability  to start downloading torrents automatically when a torrent file is available in a folder means you can start torrent downloads from anywhere, even if your computer is not accessible. Let me show how you can do this.

<!--more-->

  1. Sign up for Dropbox using this [link][3] (Disclaimer: The link is a referral link, if you signup with the referral code then I get 250MB extra space on my Dropbox.)
  2. Install Dropbox client by following the instructions [here][4].
  3. Create a private shared folder in Dropbox.
  4. Now lets configure Transmission. Launch Transmission. Click on Edit -> Preferences. Ensure that "Automatically add torrents from:" checkbox is checked, and point it to your Dropbox folder. Also ensure that Start when added is checked, Display options checkbox is unchecked and point the destination to a suitable folder.<figure id="attachment_740" aria-describedby="caption-attachment-740" style="width: 300px" class="wp-caption aligncenter">

[<img class="size-medium wp-image-740" title="transmission-options" src="https://images.sbhat.me/ss/2009/05/transmission-300x187.png" alt="transmission-options"   srcset="https://images.sbhat.me/ss/2009/05/transmission-300x187.png 300w, https://images.sbhat.me/ss/2009/05/transmission-1024x640.png 1024w, https://images.sbhat.me/ss/2009/05/transmission.png 1280w" sizes="(max-width: 300px) 100vw, 300px" />][5]<figcaption id="caption-attachment-740" class="wp-caption-text">transmission-options</figcaption></figure> 

That's it. Next time, whenever your upload a torrent file to the chosen Dropbox folder, the Dropbox client ensures that the torrent file gets pushed to your chosen folder, and Transmission will automatically start the download. Simple, isn't it ?

 [1]: https://en.wikipedia.org/wiki/Dropbox%20%28storage%20provider%29
 [2]: https://en.wikipedia.org/wiki/Transmission%20%28BitTorrent%20client%29
 [3]: https://www.getdropbox.com/referrals/NTMzNTM5
 [4]: https://www.getdropbox.com/install
 [5]: https://images.sbhat.me/ss/2009/05/transmission.png

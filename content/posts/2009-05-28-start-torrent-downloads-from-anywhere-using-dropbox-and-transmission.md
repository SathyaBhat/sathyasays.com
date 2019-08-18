---
title: Start torrent downloads from anywhere using Dropbox and Transmission
author: Sathya
type: post
date: 2009-05-28T01:20:08+00:00
url: /2009/05/28/start-torrent-downloads-from-anywhere-using-dropbox-and-transmission/
categories:
  - "Tips &amp; How-To's"
tags:
  - accessible
  - beta
  - chm
  - DE
  - download
  - downloads
  - DropBox
  - file
  - how-tos
  - IM
  - install
  - os
  - show
  - sync
  - tar
  - "tips-and-howto's"
  - torrents
  - transmission
  - tutorials
  - web
  - X

---
I&#8217;ve been using [Dropbox][1]{#aptureLink_bv4dsrVQ0J} pretty extensively ever since its private beta days and just love its simplicity and ease with which I can keep all my files in sync across multiple computers. Even more awesome is its simple web interface &#8211; just upload a file and boom, the file you uploaded gets sync&#8217;d across all your computers. This coupled with [Transmission][2]{#aptureLink_qW0FfjT1X1}&#8216;s ability  to start downloading torrents automatically when a torrent file is available in a folder means you can start torrent downloads from anywhere, even if your computer is not accessible. Let me show how you can do this.

<!--more-->

  1. Sign up for Dropbox using this [link][3] (Disclaimer: The link is a referral link, if you signup with the referral code then I get 250MB extra space on my Dropbox.)
  2. Install Dropbox client by following the instructions [here][4].
  3. Create a private shared folder in Dropbox.
  4. Now lets configure Transmission. Launch Transmission. Click on Edit -> Preferences. Ensure that &#8220;Automatically add torrents from:&#8221; checkbox is checked, and point it to your Dropbox folder. Also ensure that Start when added is checked, Display options checkbox is unchecked and point the destination to a suitable folder.<figure id="attachment_740" aria-describedby="caption-attachment-740" style="width: 300px" class="wp-caption aligncenter">

[<img data-attachment-id="740" data-permalink="https://sathyasays.com/2009/05/28/start-torrent-downloads-from-anywhere-using-dropbox-and-transmission/transmission/" data-orig-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2009/05/transmission.png?fit=1280%2C800&ssl=1" data-orig-size="1280,800" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="transmission-options" data-image-description="" data-medium-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2009/05/transmission.png?fit=300%2C187&ssl=1" data-large-file="https://i0.wp.com/sathyasays.com/wp-content/uploads/2009/05/transmission.png?fit=740%2C463&ssl=1" class="size-medium wp-image-740" title="transmission-options" src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/05/transmission-300x187.png?resize=300%2C187" alt="transmission-options" width="300" height="187" srcset="https://i0.wp.com/sathyasays.com/wp-content/uploads/2009/05/transmission.png?resize=300%2C187&ssl=1 300w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2009/05/transmission.png?resize=1024%2C640&ssl=1 1024w, https://i0.wp.com/sathyasays.com/wp-content/uploads/2009/05/transmission.png?w=1280&ssl=1 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][5]<figcaption id="caption-attachment-740" class="wp-caption-text">transmission-options</figcaption></figure> 

That&#8217;s it. Next time, whenever your upload a torrent file to the chosen Dropbox folder, the Dropbox client ensures that the torrent file gets pushed to your chosen folder, and Transmission will automatically start the download. Simple, isn&#8217;t it ?

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/05/28/start-torrent-downloads-from-anywhere-using-dropbox-and-transmission/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-739" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/05/28/start-torrent-downloads-from-anywhere-using-dropbox-and-transmission/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-739" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/05/28/start-torrent-downloads-from-anywhere-using-dropbox-and-transmission/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-739" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/05/28/start-torrent-downloads-from-anywhere-using-dropbox-and-transmission/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/05/28/start-torrent-downloads-from-anywhere-using-dropbox-and-transmission/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://en.wikipedia.org/wiki/Dropbox%20%28storage%20provider%29
 [2]: http://en.wikipedia.org/wiki/Transmission%20%28BitTorrent%20client%29
 [3]: https://www.getdropbox.com/referrals/NTMzNTM5
 [4]: https://www.getdropbox.com/install
 [5]: https://i0.wp.com/sathyasays.com/wp-content/uploads/2009/05/transmission.png
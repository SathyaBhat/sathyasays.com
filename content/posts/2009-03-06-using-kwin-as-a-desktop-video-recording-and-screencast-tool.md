---
title: Using KWin as a Desktop Video Recording and Screencast tool
author: Sathya
type: post
date: 2009-03-06T01:46:06+00:00
url: /2009/03/06/using-kwin-as-a-desktop-video-recording-and-screencast-tool/
categories:
  - "Tips &amp; How-To's"
tags:
  - capsury
  - chm
  - cpsrecode
  - DE
  - Desktop
  - exe
  - file
  - fun
  - IM
  - KDE
  - KDE 4.2
  - KWin
  - mencoder
  - os
  - plugin
  - record
  - rm
  - Screen
  - script
  - shell script
  - show
  - videos
  - X

---
Not many know of this, but as of KDE 4.2, Kwin, the window manager has a nifty little feature &#8211; it can grab videos of desktop much like a screencasting tool such as Camtasia. This functionality requires Kwin&#8217;s composition mode to be enabled (ie, you must be using Kwin&#8217;s desktop effects).

<span>Below video shows where and how you can enable the video recording feature. Note this video was recorded using <span>KWin</span>.</span>
  
<!--more-->


  
Though it isn&#8217; the best, Kwin&#8217;s video recording plugin works pretty well, but its just a basic thing.  As of now it cannot grab any audio.

Another quirk with this is that KWin saves the video recorded as a .cps file (some weird capsury format).  Before this can be view you need to recode this using a tool called cpsrecode. The quirk isn&#8217;t over yet. After recoding, I found that the video was flipped by 180 degrees and mirrored. This meant I had to use mencoder to correct it. To make this worse, mencoder can rotate only by 90 degrees at a time. Which means to get the final video you need to

  1. Recode this using cpsrecode
  2. Flip it by 90
  3. Flip it by 90 degree and mirror it

Found these rather tedious, so I chained all three to a single command, and with [Mehul][1]{#aptureLink_KpkrN7QBu9}&#8216;s help made it into a script.

So click on the link below, make the file executable by typing
  
`chmod u+x recode.sh`

To convert goto the directory where the recode.sh file is, and type
  
`<br />
./recode <input-file-name> <output-file-name>`

Here is the script: [dm]2[/dm]

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/03/06/using-kwin-as-a-desktop-video-recording-and-screencast-tool/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-710" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/03/06/using-kwin-as-a-desktop-video-recording-and-screencast-tool/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-710" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/03/06/using-kwin-as-a-desktop-video-recording-and-screencast-tool/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-710" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/03/06/using-kwin-as-a-desktop-video-recording-and-screencast-tool/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/03/06/using-kwin-as-a-desktop-video-recording-and-screencast-tool/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://blog.mehulved.com/
---
title: Using KWin as a Desktop Video Recording and Screencast tool
author: Sathya
type: post
date: 2009-03-06T01:46:06+00:00
url: /2009/03/06/using-kwin-as-a-desktop-video-recording-and-screencast-tool/
categories:
  - "Tips &amp; How-To's"
tags:
  - kwin
  - tutorials

---
Not many know of this, but as of KDE 4.2, Kwin, the window manager has a nifty little feature &#8211; it can grab videos of desktop much like a screencasting tool such as Camtasia. This functionality requires Kwin's composition mode to be enabled (ie, you must be using Kwin's desktop effects).

<span>Below video shows where and how you can enable the video recording feature. Note this video was recorded using <span>KWin</span>.</span>
  
<!--more-->


  
Though it isn' the best, Kwin's video recording plugin works pretty well, but its just a basic thing.  As of now it cannot grab any audio.

Another quirk with this is that KWin saves the video recorded as a .cps file (some weird capsury format).  Before this can be view you need to recode this using a tool called cpsrecode. The quirk isn't over yet. After recoding, I found that the video was flipped by 180 degrees and mirrored. This meant I had to use mencoder to correct it. To make this worse, mencoder can rotate only by 90 degrees at a time. Which means to get the final video you need to

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

 [1]: https://blog.mehulved.com/

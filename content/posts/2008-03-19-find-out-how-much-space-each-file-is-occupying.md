---
title: Find out how much space each file is occupying
author: Sathya
type: post
date: 2008-03-19T11:03:08+00:00
url: /2008/03/19/find-out-how-much-space-each-file-is-occupying/
categories:
  - "Tips &amp; How-To's"
tags:
  - apps
  - commands
  - console
  - DE
  - disk usage
  - Dolphin
  - download
  - downloads
  - file
  - filesystem
  - find
  - free
  - GNOME
  - hard disk
  - Home
  - how-tos
  - IM
  - KDE
  - KDirStat
  - Konqueror
  - kubuntu
  - mount
  - os
  - preview
  - review
  - rm
  - show
  - terminal
  - tips
  - Ubuntu
  - user
  - X

---
Consider this situation. You want to know much space is available on your hard disk. No big deal, du can tell you the stats. For this open the terminal and type `du -h`. You will get the required details as below

> `sathya@shaman:~$ du -h /home/sathya/Downloads`
  
> `35M     /home/sathya/Downloads/kubuntu debs`
  
> `177M    /home/sathya/Downloads`
  
> `sathya@shaman:~$ du -h /home/sathya/Downloads/kubuntu\ debs/`
  
> `35M     /home/sathya/Downloads/kubuntu debs`

But this isn&#8217;t sufficient, and neither is it very elegant. You want to know how much space each file is occupying, or what&#8217;s the max filesize occupied by a file. And you want to achieve this with out any console commands. Sounds tough?

Not really! Konqueror comes with an inbuilt &#8220;File Size View&#8221; which allows you to do just that. And the neat thing is that this works for all mounted partitons. To open this view, open Konqueror. Right click, choose Preview in and select &#8220;File Size View&#8221;

<p align="center">
  <a href="https://i1.wp.com/sathyasays.com/wp-content/uploads/2008/03/filesizwview.jpg" title="File Size View"><img src="https://i2.wp.com/sathyasays.com/wp-content/uploads/2008/03/filesizwview.thumbnail.jpg?w=740" alt="File Size View" data-recalc-dims="1" /></a>
</p>

<p align="left">
  Once this is selected, another view comes up, showing the size of each file. It may take a minute or two as the filesystem is scanned and the files begin to show up. In the end you&#8217;ll get a view like:
</p>

<p align="center">
  <a href="https://i2.wp.com/sathyasays.com/wp-content/uploads/2008/03/filesizwview1.jpg" title="File Size View, After Scanning is Complete"><img src="https://i0.wp.com/sathyasays.com/wp-content/uploads/2008/03/filesizwview1.thumbnail.jpg?w=740" alt="File Size View, After Scanning is Complete" data-recalc-dims="1" /></a>
</p>

<p align="left">
  This is really useful if you want to free up some space on your hard disk, or if you don&#8217;t know which file is taking up all that space.
</p>

<p align="left">
  PS: I don&#8217;t know of a similar utility for GNOME, as I don&#8217;t use it. Would appreciate it if any GNOME users can comment on a similar app.
</p>

PPS: If you&#8217;re using KDE 4.x , then as of now, Dolphin doesn&#8217;t have the File Size view, so you can&#8217;t check this. There&#8217;s another program, [KDirStat][1], which can perform the same utility, but I haven&#8217;t tested this. Any comment on this would be much appreciated as well!

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/03/19/find-out-how-much-space-each-file-is-occupying/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-278" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/03/19/find-out-how-much-space-each-file-is-occupying/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-278" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/03/19/find-out-how-much-space-each-file-is-occupying/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-278" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/03/19/find-out-how-much-space-each-file-is-occupying/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/03/19/find-out-how-much-space-each-file-is-occupying/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://kdirstat.sourceforge.net/ "KDirStat"
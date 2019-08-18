---
title: Writing an iso file to a CD-R/DVD-R from Linux Terminal
author: Sathya
type: post
date: 2009-03-30T01:00:37+00:00
url: /2009/03/30/writing-an-iso-file-to-a-cd-rdvd-r-from-linux-terminal/
categories:
  - News
tags:
  - Brasero
  - commands
  - DE
  - DVD
  - file
  - IM
  - iso
  - linux
  - open source
  - record
  - rm
  - root
  - script
  - shell
  - shell script
  - switch
  - terminal
  - "tips-and-howto's"
  - tutorials
  - ux
  - write
  - X

---
Ever wondered if there&#8217;s a quick and easy way to write an iso file to a CD-R/DVD-R ? Don&#8217;t want to open K3B or Brasero ? Here&#8217;s a handy way of writing the iso file.

<!--more-->


  
First, switch to root using su
  
`su`

Next, type
  
`cdrecord -scanbus`

You&#8217;ll get something like this:

> `scsibus0:<br />
0,0,0      0) 'TSSTcorp' 'DVD+-RW TS-L632H' 'D200' Removable CD-ROM<br />
0,1,0      1) *`

Note the first 3 numbers corresponding to your CD/DVD writer.
  
Next, type

`cdrecord -v dev=x,y,z <name-of-iso-file>`

replacing x,y,z with the numbers obtained in the above line and the name of iso file as well! Simple!

To make it even simpler, you can wrap the command around a shell script accepting the filename as the input for even faster access. CLI FTW!

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/03/30/writing-an-iso-file-to-a-cd-rdvd-r-from-linux-terminal/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-721" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/03/30/writing-an-iso-file-to-a-cd-rdvd-r-from-linux-terminal/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-721" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/03/30/writing-an-iso-file-to-a-cd-rdvd-r-from-linux-terminal/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-721" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/03/30/writing-an-iso-file-to-a-cd-rdvd-r-from-linux-terminal/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/03/30/writing-an-iso-file-to-a-cd-rdvd-r-from-linux-terminal/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
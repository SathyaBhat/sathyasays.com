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
---
title: Bring Back Deleted Files Using lsof
author: Sathya
type: post
date: 2008-05-07T05:17:38+00:00
url: /2008/05/07/bring-back-deleted-files-using-lsof/
categories:
  - "Tips &amp; How-To's"
tags:
  - commands
  - DE
  - delete
  - file
  - find
  - IM
  - linux
  - lsof
  - os
  - read
  - script
  - scripts
  - "tips-and-howto's"
  - tutorials
  - ux
  - X

---
Found this article while going random browsing, [the original article][1] is from [Linux.com][2] with JC Lima reccreates it, with example. Definitely worth reading

> At first it did not make a lot of sense since unless you have the file open, this will not work. How likely are you to have the files you just deleted by mistake still open?
> 
> Well, not very likely. BUT…if you own a shared hosting company, (or if you are the system administrator of one), you know that often someone will have poor code along with allow\_url\_fopen turned on, and in no time you will have hackers injecting and running scripts on your server.
> 
> Usually you are able to find the running process and kill it. But if you look at the file descriptors you may find the file that got deleted after it was ran and still in memory.

> I will have a similar example to the one in the article:

Continue reading at [Linuxzone.org][3]

 [1]: http://www.linux.com/articles/58142
 [2]: http://www.linux.com/
 [3]: http://www.linuxzone.org/?p=19
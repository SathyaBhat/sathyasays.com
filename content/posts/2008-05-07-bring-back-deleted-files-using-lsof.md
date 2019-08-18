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

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/05/07/bring-back-deleted-files-using-lsof/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-299" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/05/07/bring-back-deleted-files-using-lsof/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-299" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/05/07/bring-back-deleted-files-using-lsof/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-299" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/05/07/bring-back-deleted-files-using-lsof/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/05/07/bring-back-deleted-files-using-lsof/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://www.linux.com/articles/58142
 [2]: http://www.linux.com/
 [3]: http://www.linuxzone.org/?p=19
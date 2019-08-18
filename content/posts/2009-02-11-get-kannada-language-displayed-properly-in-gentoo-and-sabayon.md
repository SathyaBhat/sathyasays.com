---
title: Get Kannada Language displayed properly in Gentoo and Sabayon
author: Sathya
type: post
date: 2009-02-10T23:41:17+00:00
url: /2009/02/11/get-kannada-language-displayed-properly-in-gentoo-and-sabayon/
categories:
  - News
tags:
  - Arch
  - DE
  - Firefox
  - Gentoo
  - indic
  - Kannada
  - linux
  - login
  - open source
  - rm
  - root
  - Sabayon
  - support
  - switch
  - tar
  - terminal
  - "tips-and-howto's"
  - tutorials
  - user
  - X

---
Well I was browsing through some Kannada sites the other day and all I got was big blocks.
  
Turned out that Gentoo and Sabayon didn&#8217;t have support for displaying Kannada characters, though, I had no such problems with Hindi & Bengali characters [amongst others]. Changing the Character encoding in Firefox to Auto-detect or Unicode didn&#8217;t work either. After doing a bit of searching, found the solution. So open the terminal, switch to root user and type

> `emerge -av lohit-fonts`

followed by 

> `fc-cache -f -v`

Restart your X server (ie, Logout, login) and you should be set!

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/02/11/get-kannada-language-displayed-properly-in-gentoo-and-sabayon/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-699" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/02/11/get-kannada-language-displayed-properly-in-gentoo-and-sabayon/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-699" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/02/11/get-kannada-language-displayed-properly-in-gentoo-and-sabayon/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-699" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/02/11/get-kannada-language-displayed-properly-in-gentoo-and-sabayon/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/02/11/get-kannada-language-displayed-properly-in-gentoo-and-sabayon/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
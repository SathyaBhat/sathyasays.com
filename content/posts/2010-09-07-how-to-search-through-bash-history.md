---
title: '[How to] Search through Bash history'
author: Sathya
type: post
date: 2010-09-07T00:16:14+00:00
url: /2010/09/07/how-to-search-through-bash-history/
topsy_short_url:
  - http://bit.ly/aCfruU
categories:
  - "Tips &amp; How-To's"
tags:
  - Arch
  - bash
  - commands
  - history
  - IM
  - rm
  - terminal
  - "tips-and-howto's"
  - tutorials

---
Quick tip &#8211; if you use the Terminal as much as I do, ever been in a situation where you&#8217;ve written a particularly long command, and then want to issue that command again but can&#8217;t recall it ? Use the history command, and pipe it to grep to search it!

> `history | grep -i <search-term>`

This will give you all commands with the search term and the corresponding line number.

To reissue that command, type

> `!history <line-number><br />
` 

Simple, easy & effective. CLI ftw.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2010/09/07/how-to-search-through-bash-history/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-919" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2010/09/07/how-to-search-through-bash-history/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-919" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2010/09/07/how-to-search-through-bash-history/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-919" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2010/09/07/how-to-search-through-bash-history/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2010/09/07/how-to-search-through-bash-history/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
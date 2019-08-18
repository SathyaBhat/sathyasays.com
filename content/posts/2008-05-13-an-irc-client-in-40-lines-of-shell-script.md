---
title: An IRC client in 40 lines of shell script
author: Sathya
type: post
date: 2008-05-13T07:03:59+00:00
url: /2008/05/13/an-irc-client-in-40-lines-of-shell-script/
categories:
  - General
tags:
  - AA
  - clients
  - DE
  - Debian
  - dpkg
  - find
  - IM
  - install
  - irc
  - laptop
  - net
  - open source
  - os
  - programming
  - read
  - script
  - shell
  - shell script
  - support
  - X

---
While hanging out in #[IndiaTwits][1],  Shyam aka [codelust][2] brought to my attention of this post in Kragen hacks Mailing list.

> So I&#8217;m installing an OS on my laptop, and for whatever reason, the Debian Etch install disk thought it would be a good idea to initialize the whole disk to random data \*before\* rather than \*after\* the rest of the install. Writing to the whole disk takes a long time &#8212; a few hours &#8212; and so I&#8217;m left with the Debian netinst environment to play with. So I decided to IRC. Unfortunately, the only programming language I could find is sh, and there don&#8217;t seem to be any IRC clients. And I can&#8217;t get the ssh client to work &#8212; I was able to install the ssh client from the udeb on the CD-ROM with udpkg -i path/to/openssl-client-whatever.udeb. But it depends on libnsl.so.1, and I don&#8217;t know what udeb I have to install to get that. So I wrote my own IRC client in shell. The output is a little ugly, and there&#8217;s no line editing or multiple window support, but otherwise it&#8217;s just like any other IRC client to use. Almost.

Continue reading the article and get the shell script in the [mailing list][3]

Edit: Fixed the URL. Thanks to [Aalaap][4] for pointing out the error

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/05/13/an-irc-client-in-40-lines-of-shell-script/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-303" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/05/13/an-irc-client-in-40-lines-of-shell-script/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-303" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/05/13/an-irc-client-in-40-lines-of-shell-script/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-303" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/05/13/an-irc-client-in-40-lines-of-shell-script/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/05/13/an-irc-client-in-40-lines-of-shell-script/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://indiatwits.canthack.net/
 [2]: http://fatalerror.in/
 [3]: http://lists.canonical.org/pipermail/kragen-hacks/2008-February/000480.html
 [4]: http://aalaap.com/
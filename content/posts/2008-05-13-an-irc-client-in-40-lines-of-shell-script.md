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

 [1]: https://indiatwits.canthack.net/
 [2]: https://fatalerror.in/
 [3]: https://lists.canonical.org/pipermail/kragen-hacks/2008-February/000480.html
 [4]: https://aalaap.com/

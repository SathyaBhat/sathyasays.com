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
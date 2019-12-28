---
title: Ubuntu Natty to skip changelogs
author: Sathya
type: post
date: 2010-11-09T18:07:01+00:00
url: /2010/11/09/ubuntu-natty-to-skip-changelogs/
topsy_short_url:
  - https://u.sbhat.me/97gnBT
categories:
  - General
tags:
  - cat
  - commands
  - DE
  - IM
  - install
  - linux
  - media
  - move
  - Natty
  - New
  - os
  - record
  - Ubuntu
  - user

---
> Due to the continuous demand for downsizing both our installation media, as well as the install footprint, we looked for packages which we should eliminate  [&#8230;], but also for stuff that users generally don&#8217;t need and won&#8217;t miss. IMO package changelogs very much fall into the latter category, so they were very high on the &#8220;first against the wall&#8221; list. Changelogs are of course a valuable developer tool, but for those it is usually less important to have them available locally, as long as there is a convenient method to access them. For that I wrote a helper tool &#8220;apt-changelog&#8221; which retrieves it from changelogs.ubuntu.com.
> 
> apt-changelog is now shipped in apt-utils in Natty. However, there were <a href="https://lists.ubuntu.com/archives/technical-board/2010-November/000535.html" target="_blank">some concerns</a>, so we got a new compromise to just ship the top 10 changelog records, and add a comment about apt-changelog at the bottom. That way, the most interesting entries are still shipped, and developers and users will get used to
> 
> &#8220;apt-changelog&#8221;; this will provide a smoother transition, but still get rid of about 90% of the changelog size.

via [Natty: Where did my changelogs go?][1].

I think this is a pretty good move.

 [1]: https://lists.ubuntu.com/archives/ubuntu-devel-announce/2010-November/000782.html

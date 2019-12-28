---
title: 'HOWTO: Starcraft 2 on Linux with Wine'
author: Sathya
type: post
date: 2010-09-02T16:15:07+00:00
url: /2010/09/02/howto-starcraft-2-on-linux-with-wine/
topsy_short_url:
  - https://bit.ly/953X5u
categories:
  - "Tips &amp; How-To's"
tags:
  - CrossOver
  - distro
  - find
  - games
  - linux
  - menu
  - Starcraft II
  - "tips-and-howto's"
  - tutorials
  - WINE

---
> Starcraft 2 [runs] under my Linux install with no issues. Since the game&#8217;s official release a few days ago I have been getting a good bit of traffic on those two pages &#8211; so I figured I would put together a quick HOWTO for getting Starcraft 2 working on your Linux distro of choice. The game runs under [Wine][1] 1.2 and/or [Crossover][2]Games 9.1.
> 
> Crossover 9.1 Starcraft 2 is listed as &#8220;officially support&#8221; and as such you will find that it has an entry in the automated games installer. The only issue is that after the game has actually finished installing the StarCraft 2 process hangs around &#8211; meaning Crossover never actually knows that the game has finished installing and thusly never creates menu entries for it. Thank fully there is a simple fix for this &#8211; after Starcraft 2 has finished installing, open up your system monitor and look for any rogue Starcraft 2 processes and kill them off. After you have done this the CXGames installer will know that it has finished installing and will create the menu entries as it should.
> 
> [&#8230;]
> 
> It worked out of the box with my current WINE install (1.2)

via [Thoughts on Technology: HOWTO: Starcraft 2 on Linux with Wine][3].

 [1]: https://www.winehq.org/
 [2]: https://www.codeweavers.com/
 [3]: https://jeffhoogland.blogspot.com/2010/07/howto-starcraft-2-on-linux-with-wine.html
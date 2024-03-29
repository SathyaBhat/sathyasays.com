---
title: '4096-Byte Sector Hard Drives & Linux'
author: Sathyajith Bhat
type: post
date: 2010-07-13T23:02:21+00:00
url: /2010/07/14/4096-byte-sector-hard-drives-linux/

categories:
  - General
tags:

  - linux

---
> Recently, I bought a pair of those new Western Digital Caviar Green drives. These new drives represent a transitional point from 512-byte sectors to 4096-byte sectors. A number of articles have been published recently about this, explaining the benefits and some of the challenges that we'll be facing during this transition. Reportedly, Linux should unaffected by some of the pitfalls of this transition, but my own experimentation has shown that Linux is just as vulnerable to the potential performance impact as Windows XP. Despite this issue being known about for a long time, basic Linux tools for partitioning and formatting drives have not caught up.
> 
> The problem most likely to hit you with one of these drives is very slow write performance. This is caused by improper logical-to-physical sector alignment.

via [Linux Not Fully Prepared for 4096-Byte Sector Hard Drives | OS News][1].

If you're going to grab some new hard drives, the above article is worth reading. The article dates to Feb, 2010 - so I'm not sure if this situation still exists. Further more,

> These drives are on the market **now**. We've known about this issue for a LONG time, and now it's here, and we haven't fully prepared. Some distros, like Ubuntu, use "parted", which has a very nice "-align optimal" option that will do the right thing. But parted is incomplete, and we must rely on tools like fdisk for everything else. **But anyone manually formatting drives based on popular how-tos that pop up at the top of Google searches is going to cause themselves a major performance hit, because mention of this alignment issue and how to fix it is conspicuously absent**.

 [1]: https://www.osnews.com/story/22872/Linux_Not_Fully_Prepared_for_4096-Byte_Sector_Hard_Drives

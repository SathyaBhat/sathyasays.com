---
title: Mounting file system created by Wubi in other Linux distros
author: Sathya
type: post
date: 2009-11-29T09:21:38+00:00
url: /2009/11/29/mounting-file-system-created-by-wubi-in-other-linux-distros/
categories:
  - News
tags:
  - commands
  - DE
  - distro
  - distros
  - file
  - filesystem
  - Home
  - install
  - linux
  - mount
  - mounting
  - open source
  - os
  - rm
  - root
  - terminal
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - ux
  - Wubi
  - X
  - xp

---
I wasn&#8217;t aware of this tiny little thing  &#8211; the filesystem in the  file created by a Wubi install can be easily mounted as a loop device.

<!--more-->To do so, just open the Terminal and type the below:

> mount <path-to-wubi-root-disk> <path-to-where-it-should-be-mounted> -o loop

This will make the kernel auto detect the filesystem type and try to mount it. Alternatively, if you&#8217;re sure of the filesystem type, mention it explicitly

> mount -t <fs-type> <path-to-wubi-root-disk> <path-to-where-it-should-be-mounted> -o loop

Would come in very handy if someone were to migrate from Wubi install to a full install, just copy over the /home files and all files saved.

Thanks, [Bharath][1]{#aptureLink_DfqHkNP9O1}.

 [1]: http://sathyasays.com/author/bharath/
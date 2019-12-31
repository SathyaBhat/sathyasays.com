---
title: '[How To] Solution for sudo: must be setuid root problem'
author: Bharath
type: post
date: 2008-10-10T17:05:07+00:00
url: /2008/10/10/how-to-solution-for-sudo-must-be-setuid-root-problem/
categories:
  - "Tips &amp; How-To's"
tags:
  
  - commands
  - linux
  - tutorials

---
I had encountered this problem on [sudo][1]/[gksu][2] not working few months earlier.

Whenever I had to open an application with gksu it did not open at all !  I was wondering what did i do. I dint know whether  i meddled with something or is it any other configuration that created the problem.

If I type sudo in terminal I get 

```
sudo: must be setuid root
```

This is how I went about fixing it:-

  1. Open terminal and enter as root i.e. type &#8216;su' and then the root password (Please be careful while being the root). Alternatively, you can also use ur OS's live CD to mount the root partition (the partition where you have installed your OS)
  2. Next, type `chmod 4755 /usr/bin/sudo` If the command perfectly happens then as far I am able to tell sudo and gksu should work correctly.

If anyone of you are still having problems regarding this issue please post it in comments

 [1]: https://www.tech-faq.com/sudo.shtml
 [2]: https://linux.about.com/cs/linux101/g/gksu.htm

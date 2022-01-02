---
title: Mounting and Burning .iso, .mdf, .nrg(Nero) files and CD Images in Linux in 1-click
author: Sathyajith Bhat
type: post
date: 2008-11-11T04:30:47+00:00
url: /2008/11/11/mounting-and-burning-iso-mdf-nrgnero-files-and-cd-images-in-linux-in-1-click/
categories:
  - "Tips & How-To's"
tags:
  - commands
  - linux


---
A while ago, I'd written a post on [howto mount CD images][1], such as .iso, .mdf files etc via the command prompt using the mount command. In the post, among the comments, Sumeet had asked if there was a way to do all of this without having to type lengthy commands. Well yes there is! And it can't get simpler than this!

  Furious ISO Mount Tool is a an amazing little application, taking only about 256KB, and gives you a neat little interface to mount all your iso, mdf(ie, made by Alcohol 120), nrg(created using Nero) images using 1 click!
  
  <a href="https://www.flickr.com/photos/sathyabhat/3019351633/"><img class="aligncenter" src="https://farm4.static.flickr.com/3005/3019351633_6396ab88db_m.jpg" alt="Furious ISO Mount Tool" /></a>


As the above pic shows, the interface is simplistic. To mount an image, just hit the browse button, choose the image file, and hit the mount button! The image will be mounted in your home directory. Furious ISO Mount tool can also launch Brasero or Nautilus and burn the image file, and can also calculate the SHA/HD5 hash, to check that the ISO is not corrupted.
  
This app is a must-install, highly recommended app! Go install it!
  
openSUSE users, can get it from YaST, provided you have PackMan repo configured. If not, add it by clicking on YaST -> Software Repositories -> Click on ADd and Choose Community Repositories. From here select PackMan (and optionally, others too ;-) ) repositories

Debian/Ubuntu users can grab the installer from here:
  
For [32-bit(x86)][2] / For [64-bit (amd64)][3]

You can [grab the sources][4] and [recompile it as well][5].

 [1]: https://sathyasays.com/2007/12/15/mounting-iso-and-mdsmdf-files-in-linux/
 [2]: https://www.marcus-furius.com/files/FuriusIsoMount/furiusisomount_0.9.0.2-1_i386.deb
 [3]: https://www.marcus-furius.com/files/FuriusIsoMount/furiusisomount_0.9.0.2-1_amd64.deb
 [4]: https://www.marcus-furius.com/files/FuriusIsoMount/furiusisomount-0.9.0.2.tar.gz
 [5]: https://sathyasays.com/2008/07/24/how-to-compile-a-program-from-source-code-installing-from-source/

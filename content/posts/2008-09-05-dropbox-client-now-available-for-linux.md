---
title: DropBox client now available for Linux!
author: Sathya
type: post
date: 2008-09-05T17:43:49+00:00
url: /2008/09/05/dropbox-client-now-available-for-linux/
categories:
  - General
tags:
  - 8.04
  - apt-get
  - compiz
  - DE
  - Debian
  - DropBox
  - Fedora
  - file
  - filesharing
  - GNOME
  - hardy
  - install
  - linux
  - Nautilus
  - online storage
  - open source
  - os
  - repo
  - repos
  - repository
  - rm
  - synaptic
  - sync
  - syncing
  - tar
  - terminal
  - Ubuntu
  - Ubuntu 8.04
  - user
  - ux
  - X

---
Dropbox &#8211; the awesome online file-storage, and syncing utility finally gets a Linux client! The developers have been promising a Linux client since day one and though it took them a while to get it &#8211; it&#8217;s finally here!

<!--more-->

[][1]

Right now a GNOME-only interface is avialable, and here are the Links

  * [Fedora Core 9 (x86_64)][1]
  * [Fedora Core 9 (x86)][2]
  * [Ubuntu 8.04 (x86_64)][3]
  * [Ubuntu 8.04 (x86)][4]
  * [Sources][5]

<div>
  Debian & Ubuntu users don&#8217;t have to deal with messy .deb files listed above, just edit your /etc/apt/sources.list file and add the following lines   </p> 
  
  <blockquote>
    <p>
      <code>deb https://www.getdropbox.com/static/ubuntu hardy main&lt;br />
deb-src https://www.getdropbox.com/static/ubuntu hardy main</code>
    </p>
  </blockquote>
  
  <p>
    and you can get it via apt-get or Synaptic through DropBox&#8217;s repository.
  </p>
  
  <p>
    Note that after installing you&#8217;ll have to restart nautilus, for this just logout and log back in, else just type
  </p>
  
  <blockquote>
    <p>
      <code>killall nautilus</code>
    </p>
  </blockquote>
  
  <p>
    at the terminal. Note that typing the above command while Compiz is enabled can lock up your PC, so just logout and log back in instead.
  </p>
</div>

 [1]: https://dl.getdropbox.com/u/5143/dblinux/nautilus-dropbox-0.4.0-1.fc9.x86_64.rpm
 [2]: https://dl.getdropbox.com/u/5143/dblinux/nautilus-dropbox-0.4.0-1.fc9.i386.rpm
 [3]: https://dl.getdropbox.com/u/5143/dblinux/nautilus-dropbox_0.4.0-1_amd64.deb
 [4]: https://dl.getdropbox.com/u/5143/dblinux/nautilus-dropbox_0.4.0-1_i386.deb
 [5]: https://dl.getdropbox.com/u/5143/dblinux/nautilus-dropbox-0.4.0.tar.bz2

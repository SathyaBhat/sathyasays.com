---
title: Fixing No Sound Bug on Dell Inspiron 1520 in Ubuntu Gutsy
author: Sathya
type: post
date: 2007-12-09T06:49:40+00:00
url: /2007/12/09/fixing-no-sound-bug-on-dell-inspiron-1520-in-ubuntu-gutsy/
categories:
  - "Tips &amp; How-To's"
tags:
  - ALSA
  - apt-get
  - boot
  - cat
  - codecs
  - DE
  - Dell
  - driver
  - DVD
  - Gutsy Gibbon
  - hassles
  - IM
  - indic
  - Inspiron
  - install
  - intel
  - internet
  - kubuntu
  - linux
  - move
  - net
  - New
  - open source
  - openSuSE
  - os
  - rm
  - sudo
  - SUSE
  - switch
  - switching
  - tar
  - terminal
  - testing
  - Ubuntu
  - update
  - ux
  - X

---
Though it&#8217;s been a while since Gutsy was released, I couldn&#8217;t try out for various reasons. But finally I got my hands on Gutsy DVD edition, and I sat about installing it on my Dell Inspiron. I noticed first signs of trouble when Gutsy was taking unsually long to boot up. Switching to verbose mode, I knew something wrong when I saw

> <font size="2"></font><font color="#008000">hda_intel: azx_get_response <strong>timeout</strong></font>

Initially I thought it was a problem with the live environment, however when install was done, my fears were confirmed. Indeed, Ubuntu wasn&#8217;t able to play any sound. This was a bit surprising since openSUSE 10.3 detected all of my hardware flawlessly(even more weirder was that Kubuntu Feisty had no problems with the sound!)

A bit of Googling and I found there are few solutions to this problem, which is because of ALSA. Apparently version lower than 1.0.15 has bugs and problems especially with Intel HDA codecs. So let&#8217;s see some solutions:

<!--more-->

### Solution 1:

The most common solotion given was to open up terminal and type

> <font color="#008000"><code>sudo apt-get install module-assistant&lt;br />
sudo m-a update&lt;br />
sudo m-a prepare&lt;br />
sudo m-a a-i alsa</code></font>

However I couldn&#8217;t try this, since I didnt have an active net connection.

### Solution 2:

Another solution is to obtain ALSA-1.0.15 and compile it from sources, as indicated below

> <font color="#008000"><code>sudo apt-get install libc6-dev&lt;br />
sudo apt-get install patch&lt;br />
w get ftp : // ftp.alsa-project.org/pub/driver/alsa-driver-1.0.15.tar.bz2 (remove the spaces after ftp and the colon, and in between w and get)&lt;br />
tar xvpjf alsa-driver-1.0.15.tar.bz2&lt;br />
cd alsa-driver-1.0.15&lt;br />
./configure --with-cards=hda-intel,emu10k1&lt;br />
make&lt;br />
sudo make install </code></font>

Again, lack of an active internet connection prevented me from testing this out. Then I came across solution 3, which was easiest of the lot.

### Solution 3:

Here, open the terminal and type

> <font color="#008000"><code>sudo apt-get install linux-backports-modules-generic</code></font>

This works great! If you want to obtain the packages from the DVD use aptitude instead of apt-get, ie

> <font color="#008000"><code>sudo aptitude install linux-backports-modules-generic</code></font>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/12/09/fixing-no-sound-bug-on-dell-inspiron-1520-in-ubuntu-gutsy/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-189" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/12/09/fixing-no-sound-bug-on-dell-inspiron-1520-in-ubuntu-gutsy/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-189" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/12/09/fixing-no-sound-bug-on-dell-inspiron-1520-in-ubuntu-gutsy/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-189" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/12/09/fixing-no-sound-bug-on-dell-inspiron-1520-in-ubuntu-gutsy/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/12/09/fixing-no-sound-bug-on-dell-inspiron-1520-in-ubuntu-gutsy/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
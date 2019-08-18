---
title: 'openSuSE 10.3: Sneak Peaks Part II, Faster Boot Times'
author: Sathya
type: post
date: 2007-09-09T17:12:31+00:00
url: /2007/09/09/opensuse-103-sneak-peaks-part-ii-faster-boot-times/
categories:
  - News
tags:
  - Arch
  - beta
  - boot
  - DE
  - ext3
  - file
  - find
  - grub
  - IM
  - install
  - linux
  - login
  - LTS
  - LV
  - LVM
  - move
  - net
  - openSuSE
  - read
  - review
  - rm
  - Screen
  - script
  - scripts
  - support
  - SUSE
  - tar
  - trivia
  - Ubuntu
  - update
  - user
  - ux
  - vm
  - X
  - YaST
  - zypper

---
openSUSE 10.3 will include some great improvements to the init boot scripts which will dramatically decrease the time your computer takes to boot up. These come as the result of many different tests and research (documented [here][1], and [here][2]); the first round of improvements have already been submitted and will make it into the final release.

<span id="more-104"></span>

## Tests and Rainy Days

Several tests were run by Frank Ruell including using the [fcache kernel patch][3], Ubuntu’s SysV init replacement [upstart][4], and the ext3 block remapper. This motivated [Stephan Kulow][5], now openSUSE’s Project Manager, to start some work on it during [one rainy weekend][6]. The results are incredibly impressive, so we ran some extra tests with [bootchart][7] to get some specific figures.

All the results below are from a Sony Vaio VGN-FE11S, with completely default installs, local users, and IP configured via DHCP. Booting in openSUSE 10.2 was unfortunately pretty slow. To get from the Boot Loader screen (GRUB) to the login screen (KDM used throughout) it took around a painful 55 seconds; in <a href="http://news.opensuse.org/?p=106" target="_blank">openSUSE 10.3 Beta 1</a> this has been reduced to just 27 seconds!

Below are the respective bootcharts:

[<img src="https://i1.wp.com/news.opensuse.org/wp-content/uploads/2007/08/bootchart-kdm_thumb.jpg?w=740" title="openSUSE 10.2 - boot to KDM" alt="openSUSE 10.2 - boot to KDM" border="0" data-recalc-dims="1" />][8] [<img src="https://i2.wp.com/news.opensuse.org/wp-content/uploads/2007/08/bootchart-27_thumb.jpg?w=740" title="openSUSE 10.3 - boot to KDM" alt="openSUSE 10.3 - boot to KDM" border="0" data-recalc-dims="1" />][9]

## Talk with Stephan Kulow

To find out just what changed and to get more information we talked to the man himself.

### What exactly did you end up changing?

One thing that is obvious in your 10.2 bootchart is that ZMD significantly delays the start-up time and we managed to get rid of it due to [libzypp][10] and [zypper][11]. We moved out all kinds of boot scripts from the default installation that were scanning hardware on boot. So now we just rely on YaST to e.g. install lvm2 if there is a lvm setup. I also patched startpar (our “initng” that we have had since about forever  <img src="https://i1.wp.com/news.opensuse.org/wp-includes/images/smilies/icon_smile.gif?w=740" alt=":)" class="wp-smiley" data-recalc-dims="1" />) to prefer xdm startup over everything else.

I reviewed all sleeps during startup and shutdown to see if they can’t be replaced by something useful and I reviewed everything that is started before *dm to see if it really is necessary. For example, we now delay the firewall setup until the network startup itself is actually due. In the past it used to be started before everything, which was really more secure than necessary. I also optimized the preload lists so that we only preload stuff that specifically _improves_ the boot time Oh, and we found one big bug &#8211; SaX2 wrote support for xfs into the default X config, which in itself caused a 5s sleep if you do not have xfs.

### I noticed that shutdown time has also significantly decreased. What happened there?

On shutdown I saved 8s in not waiting for things by simply sleeping and instead to simply poll the event we are waiting for.

### Any plans for the future?

For trivial changes there is only really potential for another 1-2s, but the big plan we have is online defragmenting. People claiming that you do not need to defragment on Linux must never boot. On your 10.2 installation above for example, after 2-5 system updates it would probably take 80s to boot instead. This is because doing updates fragments the files you need to boot, so you seek a lot and that causes more delays.

You can see Fengguang Wu’s [Boot Linux Faster][12] talk for more information.

From: [openSuSE][13]

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-ii-faster-boot-times/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-45" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-ii-faster-boot-times/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-45" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-ii-faster-boot-times/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-45" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-ii-faster-boot-times/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-ii-faster-boot-times/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://opensuse.org/Boottime
 [2]: http://opensuse.org/Boot_time
 [3]: http://en.opensuse.org/Fcache-howto
 [4]: http://en.opensuse.org/Ubuntu_and_Upstart
 [5]: http://news.opensuse.org/?p=112 "People of openSUSE: Stephan Kulow"
 [6]: http://www.kdedevelopers.org/node/2840
 [7]: http://bootchart.org/
 [8]: https://i1.wp.com/news.opensuse.org/wp-content/uploads/2007/08/bootchart-kdm.png "openSUSE 10.2 - boot to KDM"
 [9]: https://i1.wp.com/news.opensuse.org/wp-content/uploads/2007/08/bootchart-27.png "openSUSE 10.3 - boot to KDM"
 [10]: http://opensuse.org/Libzypp
 [11]: http://opensuse.org/Zypper
 [12]: http://pagecache-tools.googlecode.com/svn/trunk/doc/boot_linux_faster/boot_linux_faster.pdf
 [13]: http://news.opensuse.org/?p=104
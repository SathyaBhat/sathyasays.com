---
title: openSUSE 11 Alpha 1
author: Sathya
type: post
date: 2008-01-20T09:17:22+00:00
url: /2008/01/20/opensuse-11-alpha-1-2/
categories:
  - News
tags:
  - /dev
  - boot
  - DE
  - Desktop
  - download
  - fun
  - IM
  - install
  - KDE
  - linux
  - LV
  - media
  - mount
  - net
  - NetworkManager
  - New
  - open source
  - openSuSE
  - openSUSE 11
  - openSUSE 11.0
  - os
  - Qt
  - software
  - SUSE
  - tar
  - testing
  - theme
  - updating
  - ux
  - X

---
With the new year beginning we kick start major development into the next version of openSUSE: openSUSE 11.0. A very early alpha version, Alpha 1, is now available for download and testing.

<div align="center">
  <a href="https://i2.wp.com/news.opensuse.org/wp-content/uploads/2008/01/installer.jpg" title="openSUSE 11.0 Alpha 1 Installer"><img src="https://i2.wp.com/news.opensuse.org/wp-content/uploads/2008/01/installer-thumb.jpg?w=740" alt="openSUSE 11.0 Alpha 1 Installer" data-recalc-dims="1" /></a><br /> The Beautiful New Look of the Installer
</div>

Despite many other products being developed in parallel to [Factory][1],
  
we have seen a heavy stream of development on it, so it is really worth
  
a try if you have time for testing. Note, however, that it is not
  
suitable for production systems.

### Changes since openSUSE 11.0 Alpha 0

We have seen 1026 package check-ins since Alpha0 and countless bugs fixed. The main changes against Alpha0 are:

  * [Sat Solver][2] integration 
      * Michael Schröder’s “sat solver” library is now the default package
  
        solver for libzypp, so make sure you doublecheck the selected packages
  
        &#8211; there might be suprises ahead. Please note that we need test cases
  
        for things that look funny to you ([wiki link][3])
  * Heavy [changes to the appearance of the Qt installation][4] (ported to qt4) 
      * Note that it’s still in draft state and your feedback is welcome
  * KDE 4.0.0
  * perl 5.10
  * glibc 2.7
  * NetworkManager 0.7
  * CUPS 1.3.5
  * Pulseaudio

### Most Annoying Bugs

Due to the huge amount of changes, there are also several noticeable bugs:

  * The new solver does not yet have a “ignore this requirement”
  
    choice, i.e. it’s not possible to create a broken system. We’re still
  
    discussing if this is a bug or a feature  <img src="https://i1.wp.com/news.opensuse.org/wp-includes/images/smilies/icon_smile.gif?w=740" alt=":)" class="wp-smiley" data-recalc-dims="1" />
  * the CDs lack a huge amount of software. Many packages had to be
  
    taken out to make way for others. The CDs should still have a a
  
    completely working desktop, however.
  * the Qt port and its theme are early releases and create noticeably
  
    more flickering and drawing glitches, e.g. the progress bar is only
  
    visible on some installations
  * jpackage packages are broken and one package will complain during installation &#8211; just ignore
  * the installation crashes at the end when creating the x11 proposal:
  
    in this case, your desktop will still have a working X config, it just
  
    might not be the perfect one. You may need to call _sax2_ after it happens
  * PPC cannot be installed as the bootloader config can’t be written
  
    out. However, you can get a working PPC system when updating from alpha0

### Media and Download

Please refer to **[software.openSUSE.org/developer][5]** for direct links to all the available media.

Have a lot of fun!

Technorati Tags: <a class="performancingtags" href="http://technorati.com/tag/openSUSE" rel="tag">openSUSE</a>, <a class="performancingtags" href="http://technorati.com/tag/linux" rel="tag">linux</a>, <a class="performancingtags" href="http://technorati.com/tag/sathyasays.com" rel="tag">sathyasays.com</a>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/01/20/opensuse-11-alpha-1-2/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-242" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/01/20/opensuse-11-alpha-1-2/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-242" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/01/20/opensuse-11-alpha-1-2/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-242" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/01/20/opensuse-11-alpha-1-2/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/01/20/opensuse-11-alpha-1-2/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://opensuse.org/Factory
 [2]: http://en.opensuse.org/Libzypp/Sat_Solver
 [3]: http://en.opensuse.org/Bugs/YaST#I_want_to_report_a_bug_related_to_package_dependencies_and_libzypp_solver._Which_logs_to_attach.3F
 [4]: http://www.kdedevelopers.org/node/3119
 [5]: http://software.opensuse.org/developer
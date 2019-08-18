---
title: 'openSuSE 10.3: Sneak Peaks Part I, 1-Click Install'
author: Sathya
type: post
date: 2007-09-09T17:07:53+00:00
url: /2007/09/09/opensuse-103-sneak-peaks-part-i-1-click-install/
categories:
  - News
tags:
  - 1-click install
  - applications
  - Arch
  - beta
  - cat
  - community
  - DE
  - disk usage
  - file
  - Firefox
  - free
  - guide
  - guides
  - IM
  - install
  - Konqueror
  - move
  - New
  - openSuSE
  - os
  - read
  - repo
  - repos
  - repositories
  - repository
  - rpm
  - show
  - software
  - SUSE
  - Unity
  - update
  - user
  - web
  - X

---
Today we are taking a look at the new _One-Click Install_ technology which aims to simplify package management for users. We will see how this is integrated into the openSUSE Build Service and we’ll have a talk with Benjamin Weber, the original author and maintainer of _One-Click Install_.

## One-Click Install: Hassle-Free Installation of Software

openSUSE contains thousands of packages that are often spread across various repositories. Great places like the [Packman project][1], [Guru’s RPM site][2] and of course the [openSUSE Build Service][3] provide thousands of packages for openSUSE users. The problem, however, is frequently the hassle of locating the package, adding the repository that contains it, and then finally installing the package. This can be a tiresome process particularly if you are intending to use many packages from different repositories (say, in the Build Service).

[One Click Install][4] removes this hassle.

<span id="more-133"></span>

In openSUSE 10.3, if you are looking to install an application from the openSUSE Build Service you can now use the new [web front-end][5] to search, browse and install applications with a single click. An example search for Filelight (an application for visualizing disk usage on your computer) in openSUSE Factory is shown below:

<p align="center">
  <a href="https://i0.wp.com/news.opensuse.org/wp-content/uploads/2007/08/search-filelight.png" title="Example Search for Filelight"><img src="https://i0.wp.com/news.opensuse.org/wp-content/uploads/2007/08/search-filelight.png?resize=492%2C379" alt="Example Search for Filelight" style="border: 1px solid #cccccc; padding: 2px" title="Example Search for Filelight" height="379" width="492" data-recalc-dims="1" /></a>
</p>

Once you click on _1-Click Install_ you are guided through a wizard that guides you through the simple process of installation the application. It will automatically add the repository for you and install the package. This process is demonstrated below:

<p align="center">
  <a href="https://i2.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-1.png" title="Start-Up Screen"><img src="https://i1.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-1_thumb.jpg?w=740" alt="Start-Up Screen" data-recalc-dims="1" /></a> <a href="https://i0.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-2.png" title="Summary"><img src="https://i2.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-2_thumb.jpg?w=740" alt="Summary" data-recalc-dims="1" /></a> <a href="https://i2.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-3.png" title="Downloading Repository Metadata"><img src="https://i1.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-3_thumb.jpg?w=740" alt="Downloading Repository Metadata" data-recalc-dims="1" /></a><br /> <a href="https://i0.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-4.png" title="Downloading Package"><img src="https://i2.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-4_thumb.jpg?w=740" alt="Downloading Package" data-recalc-dims="1" /></a> <a href="https://i1.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-5.png" title="Installing Package"><img src="https://i1.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-5_thumb.jpg?w=740" alt="Installing Package" data-recalc-dims="1" /></a> <a href="https://i0.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-6.png" title="Finished"><img src="https://i1.wp.com/news.opensuse.org/wp-content/uploads/2007/08/one-click-install-6_thumb.jpg?w=740" alt="Finished" data-recalc-dims="1" /></a> <a href="http://news.opensuse.org/wp-content/uploads/2007/08/one-click7.png" title="Finished"> </a>
</p>

This can all be tested right _now_ presuming you are running [openSUSE 10.3 Beta 1][6] or current [openSUSE Factory][7] with Konqueror. To get it running in Firefox check [this walkthrough][8].

This new capability will also be used across [openSUSE-Community.org][9] in the future. The [Software Search][10] there also has an [updated version][11] in the works using the same One-Click Install technology. Below is, once again, an example search for _filelight_:

<p align="center">
  <a href="https://i0.wp.com/news.opensuse.org/wp-content/uploads/2007/08/software-search-install.png" title="Software Search"><img src="https://i0.wp.com/news.opensuse.org/wp-content/uploads/2007/08/software-search-install.png?resize=455%2C302" alt="Software Search" style="border: 1px solid #cccccc; padding: 2px" height="302" width="455" data-recalc-dims="1" /></a>
</p>

Clicking on one of those links will take you through the same simple wizard as above.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-i-1-click-install/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-44" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-i-1-click-install/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-44" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-i-1-click-install/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-44" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-i-1-click-install/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2007/09/09/opensuse-103-sneak-peaks-part-i-1-click-install/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://packman.links2linux.org/
 [2]: http://linux01.gwdg.de/%7Epbleser/
 [3]: http://opensuse.org/Build_Service
 [4]: http://en.opensuse.org/Standards/One_Click_Install
 [5]: http://software.opensuse.org/search
 [6]: http://news.opensuse.org/?p=106
 [7]: http://opensuse.org/Factory
 [8]: http://dev.beryl-project.org/%7Ecyberorg/suse/49/one-click-install-opensuse-build-service/
 [9]: http://opensuse-community.org/ "openSUSE Community"
 [10]: http://packages.opensuse-community.org/ "openSUSE Software Search"
 [11]: http://benjiweber.co.uk:8080/webpin/index-test.jsp
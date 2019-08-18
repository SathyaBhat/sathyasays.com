---
title: Disabling Auto-Refresh of Repositories in openSUSE 11
author: Sathya
type: post
date: 2008-08-18T15:27:31+00:00
url: /2008/08/18/disabling-auto-refresh-of-repositories-in-opensuse-11/
categories:
  - "Tips &amp; How-To's"
tags:
  - apt-get
  - DE
  - Debian
  - dl
  - download
  - downloads
  - DVD
  - IM
  - install
  - linux
  - open source
  - openSuSE
  - openSUSE 11
  - os
  - package manager
  - repo
  - repos
  - repositories
  - rm
  - RMS
  - software
  - subs
  - SUSE
  - synaptic
  - "tips-and-howto's"
  - tutorials
  - X
  - YaST

---
One of the heavily improved aspects of openSUSE 11 is the package manager and the way packages and repositories are handled. Although YaST [Yet Another Setup Tool, openSUSE&#8217;s system admin/configuration tool] is no longer the slow poke that it used to be, its still no match in terms of speed to Debian&#8217;s apt-get/Synaptic.
  
One of the more irritating part of YaST is that it auto-refreshes the repositories every time you launch the package management tool.ie, YaST downloads the info regarding all the packages that are available in the repo. Now if you&#8217;ve subscribed to multiple repos(most likely the case) or if you&#8217;re stuck on a slow connection, this can take the wind out of your sails, especially if you want to jsut install something from the DVD. So here&#8217;s a small step to disable auto-refresh of repos.
  
First head over to YaST, click on Software and then Software Repositories.

<p style="text-align: center;">
  <a href="http://sathyasays.com/wp-content/uploads/2008/08/softrepo1.png"><img class="alignnone size-thumbnail wp-image-337" title="softrepo1" src="http://sathyasays.com/wp-content/uploads/2008/08/softrepo1-150x150.png" alt="" width="150" height="150" /></a>
</p>

Next,Select the repo, and ensure that Automatically refresh is disabled. That&#8217;s it!

<p style="text-align: center;">
  <a href="http://sathyasays.com/wp-content/uploads/2008/08/refresh.png"><img class="aligncenter size-thumbnail wp-image-336" title="refresh" src="http://sathyasays.com/wp-content/uploads/2008/08/refresh-150x150.png" alt="" width="150" height="150" /></a>
</p>

The repos will no longer refresh automatically.
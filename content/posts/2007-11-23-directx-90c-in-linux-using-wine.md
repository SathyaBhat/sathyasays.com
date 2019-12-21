---
title: DirectX 9.0c in Linux using WINE
author: Sathya
type: post
date: 2007-11-23T15:10:42+00:00
url: /2007/11/23/directx-90c-in-linux-using-wine/
categories:
  - "Tips &amp; How-To's"
tags:
  - 3D
  - applications
  - blog
  - cat
  - Convention
  - DE
  - Desktop
  - DirectX
  - dl
  - driver
  - games
  - IM
  - install
  - linux
  - media
  - Microsoft
  - multimedia
  - music
  - New
  - os
  - programming
  - read
  - review
  - RIA
  - rm
  - RMS
  - software
  - tar
  - ux
  - windows
  - WINE
  - X

---
I found this blog giving a step-by-step tutorial on how to get Direct 9.0c installed on your Linux box. Worthy of a look I say!

Excerpts:

**About DirectX**

Microsoft DirectX is a collection of application programming interfaces for handling tasks related to multimedia, especially game programming and video, on Microsoft platforms. Originally, the names of these APIs all began with Direct, such as Direct3D, DirectDraw, DirectMusic, DirectPlay, DirectSound, and so forth. DirectX, then, was the generic term for all of these Direct-something APIs, and that term became the name of the collection. Over the intervening years, some of these APIs have been deprecated and replaced, so that this naming convention is no longer absolute. In fact, the X has caught on to the point that it has replaced Direct as the common part in the names of new DirectX technologies, including XAct, XInput, and so forth.

<!--more-->

Direct3D (the 3D graphics API within DirectX) is widely used in the development of computer games for <span>Microsoft </span><span>Windows</span>, Microsoft Xbox, and Microsoft Xbox 360. Direct3D is also used by other software applications for visualization and graphics tasks, most notably among the engineering sector for CAD/CAM, because of its ability to quickly render high-quality 3D graphics using DirectX-compatible graphics hardware. As Direct3D is the most widely recognized API in DirectX, it is not uncommon to see the name DirectX used in place of Direct3D.

**Wine configuration**

This is with a clean configuration directory and running in a 1024&#215;768 virtual desktop.

$ winecfg

Once the .wine directory is built the configuration tool will start and you can set a virtual desktop in the graphics tab if you wish. This is a good time to also set your Audio driver in the Audio tab.

next up is to install a native mscoree.dll and streamci.dll into /system32 from a windows install and set them to native Windows.

You will need to set a large number of dlls to native for the install to work properly. Here is the full list of dlls that needs to be set.[Continue reading at Wine Review][1]

 [1]: http://wine-review.blogspot.com/2007/11/directx-90c-on-linux-with-wine.html
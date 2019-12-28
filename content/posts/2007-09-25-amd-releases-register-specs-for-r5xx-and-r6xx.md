---
title: AMD Releases Register Specs For R5xx And R6xx
author: Sathya
type: post
date: 2007-09-25T15:37:11+00:00
url: /2007/09/25/amd-releases-register-specs-for-r5xx-and-r6xx/
categories:
  - News
tags:
  - 3D
  - blog
  - cat
  - community
  - DE
  - driver
  - drivers
  - Fedora
  - IM
  - linux
  - Novell
  - open source
  - openSuSE
  - os
  - rm
  - support
  - SUSE
  - Unity
  - user
  - ux
  - X

---
Last week, AMD released register specifications for the RV630 and M56 parts into open source, thus allowing the OSS community to develop 2D (and theoretically 3D) drivers, given time. Current documentation for the project is available over at [X.Org.][1]

Now, eight days later, Novell has [released][2] an alpha-quality driver for the R6XX and R5XX series of cards. The current alpha allows for initial mode settings, and the devs plan to add support for additional hardware, RandR 1.2, video overlay support, and 2D acceleration. More information is available at the openSUSE blog, and the driver is available for multiple distribution packages—Fedora, Mandriva, and SUSE Linux Enterprise. The Linux userbase has called for open sourced drivers from the major manufacturers for years. Obviously AMD/ATI&#8217;s source code release is only one step towards such a development, and current work is focused on 2D, rather than 3D acceleration, but this type of information sharing could conceivably lead to an OSS 3D driver, given enough time and effort.

Given that ATi users generally have had problems under Linux due to ATi&#8217;s non disclosure of hardware details, and volunteers having to reverse engineer to get ussable drivers, this should hopefully reduce ATi users&#8217; frustrations.

Source: [Joel Hruska][3] from [Ars Technica][4]

 [1]: https://www.x.org/docs/AMD
 [2]: https://news.opensuse.org/?p=265
 [3]: https://arstechnica.com/authors.ars/DpuTiger
 [4]: https://arstechnica.com/journals/linux.ars/2007/09/21/amdati-release-register-specifications-novell-follows-with-alpha-driver

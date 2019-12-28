---
title: '10 Rocking Feature in 10 Days: AppArmor'
author: Sathya
type: post
date: 2007-10-16T11:03:15+00:00
url: /2007/10/16/10-rocking-feature-in-10-days-apparmor/
categories:
  - News
tags:
  - 8.04
  - AA
  - AIR
  - applications
  - beta
  - cat
  - cover
  - DE
  - exploit
  - file
  - hardy
  - Hardy Heron
  - Heron
  - IM
  - New
  - Novell
  - openSuSE
  - os
  - read
  - RIA
  - rm
  - software
  - SUSE
  - talks
  - tar
  - Ubuntu
  - Ubuntu 8.04
  - user
  - X
  - xp

---
[Corey Burger][1] talks about Novell&#8217;s AppAPrmour implementation in Gutsy in the 7th part of the series:

**So what does AppArmor do?**

AppArmor helps you keep your computer secure by restricting what certain applications can do. This means that if somebody discovers a new way to exploit protected software, AppArmor helps reduce the risk by limiting access to resources defined in the application profile.

**So what sort of profiles are currently enabled in Gutsy**

Currently 7.10 ships with the framework and all the application tools, although only CUPS (the printing tool) has a profile enforced by default. The plan for Ubuntu 8.04 (called Hardy Heron in it’s development cycle) is to have a larger set of profiles enabled.

However, there is a beta profiles package in the universe component cunningly named _apparmor-profiles_. These profiles are in what is called “complain” mode, which warns the user that an application is doing something wrong without actually stopping it. The complain mode contrasts with the “enforce” mode, which does exactly that.

**So how do I make an AppArmor profile?**

If you are an end user or a sysadmin that wants to help out with the development of Ubuntu or AppArmor or merely needs to create a profile for an application they use, it is fairly easy. AppArmor builds in easy tools to profile applications and create profiles. A great tutorial to get started can be found on the [AppArmor page][2] on the help wiki.

**So will this break my system?**

Nope! One of the key reasons this is being rolled across two releases (the framework in 7.10, the profiles in 8.04) is to eliminate such issues.

**What if I screw with AppArmor and it goes boink?**

Hey, there is an answer for that too. AppArmor builds in a cool little utility called _aa-logprof_ to help fix AppAmor and get you a working system again. You can read more about aa-logprof on the [AppArmor page][2] too.

**Got any shiny pictures of AppArmor in action?**

Nope. AppArmor is designed to be one of those silent things that you never notice.

If you want to read more about AppArmor, aside from the Ubuntu Help page, you can also try the OpenSuse page on [AppArmor][3]

See you all tomorrow!

 [1]: https://fridge.ubuntu.com/node/1175
 [2]: https://help.ubuntu.com/community/AppArmor
 [3]: https://en.opensuse.org/Apparmor

---
title: Enabling And Disabling Root Account in Debian/Ubuntu
author: Sathya
type: post
date: 2008-05-27T04:30:35+00:00
url: /2008/05/27/enabling-and-disabling-root-account-in-debianubuntu/
categories:
  - "Tips &amp; How-To's"
tags:
  - Debian
  - linux
  - tutorials


---
<span style="text-decoration: line-through;">Debian and other debian-based distros like</span> Ubuntu <span style="text-decoration: line-through;">have</span>, by default, has the root account disabled as a security measure.(thanks to Subbu and PICCORO for the clarification)

To re-enable the root account, just open the command prompt, and type

> `sudo passwd root`

You'll get the following set of messages:

> `sathya@sathya-laptop:~$ sudo passwd root<br />
Enter new UNIX password:<br />
Retype new UNIX password:<br />
passwd: password updated successfully<br />
sathya@sathya-laptop:~$`

To disable root access, just type

> `sudo passwd -l root`

If you're weary of using the command line(you shoudn't ;) ) then there's another way:
  
Just head over to System > Administration > Login Window > Security > and check mark the box beside Allow local system administrator login.

DISCLAIMER: Christof Baumann mentions in [**this**][1] post as to why you shouldn't fiddle with the root account:

> Be aware of locking the root account if you once activated it. I activated the root account and skipped the %admin ALL=(ALL) ALL line int /etc/sudoers file because i thought i wouldn’t need it anymore. Then i disabled the root account without thinking and now had no chance to start programs with root rights. Luckily i could restore it using a knoppix live cd. Be aware of changing settings concerning the root account.

Also, read [**this**][2] article in Ubuntu Wiki as to why sudo is preferred over standard root account.

PS: Just incase you guys are wondering why I've posted this basic info so late, well I'm just getting the hang of Ubuntu.

 [1]: https://www.ducea.com/2006/06/21/ubuntu-how-to-enable-the-root-account/
 [2]: https://help.ubuntu.com/community/RootSudo

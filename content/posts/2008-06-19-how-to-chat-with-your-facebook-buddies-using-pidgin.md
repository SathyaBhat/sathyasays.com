---
title: '[How To] Chat With Your Facebook Buddies Using Pidgin'
author: Sathya
type: post
date: 2008-06-19T12:08:43+00:00
url: /2008/06/19/how-to-chat-with-your-facebook-buddies-using-pidgin/
categories:
  - "Tips &amp; How-To's"
tags:
  - cat
  - DE
  - Debian
  - dl
  - exe
  - Facebook
  - file
  - how-tos
  - icons
  - IM
  - install
  - linux
  - messenger
  - Nokia
  - open source
  - os
  - Pidgin
  - plugin
  - root
  - tar
  - "tips-and-howto's"
  - tutorials
  - Ubuntu
  - user
  - ux
  - windows
  - X

---
Recently, [Facebook][1] introduced [Facebook chat][2] &#8211; which allows you to chat with your Facebook friends in realtime similar to IM, as compared to post-message-on-wall-and-wait-for-replies kinda communication that Facebook users endured so far. A slight problem would be that to use this feature, users need to be logged in and be on Facebook&#8217;s site.

Not any more. [eionrobb][3] and [Saturn2888][4] have coded a plugin for [Pidgin][5] which allows you to chat with your facebook buddies using the Facebook Chat IM service. Just grab the [plugin][6] [][6](.[deb][7] installer for Debian and its derivatives like Ubuntu, [.exe][8] installer for Windows, and [sources][6] available), copy the the .dll file to your C:\Program Files\Pidgin\plugins\ (or equivalent) directory and restart Pidgin, if you&#8217;re on Windows.

For Linux users copy one of the .so files to either /usr/lib/purple-2/ (for 32-bit Linux), /usr/lib64/purple-2/ (for 64-bit Linux), /usr/lib/pidgin/ (for Nokia/Maemo) or ~/.purple/plugins/ (if you don&#8217;t have root access) and restart Pidgin.

Don&#8217;t forget to grab the icons too. Just Extract the facebook_icons.zip file to the pixmaps/pidgin/protocols folder. On Windows this is generally C:\Program Files\Pidgin\pixmaps\pidgin\protocols and on Linux, /usr/share/pixmaps/pidgin/protocol and enjoy chatting.

 [1]: https://facebook.com
 [2]: https://blog.facebook.com/blog.php?post=12811122130
 [3]: https://code.google.com/u/eionrobb/
 [4]: https://code.google.com/u/Saturn2888/
 [5]: https://www.pidgin.im/
 [6]: https://code.google.com/p/pidgin-facebookchat/
 [7]: https://pidgin-facebookchat.googlecode.com/files/pidgin-facebookchat-1.16.deb
 [8]: https://pidgin-facebookchat.googlecode.com/files/pidgin-facebookchat-1.16.exe

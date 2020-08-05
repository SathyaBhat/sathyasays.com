---
title: '[How to] Fix “Home Directory should be accesible only by the user” — Warning Message during login'
author: Bharath
type: post
date: 2008-10-25T06:44:39+00:00
url: /2008/10/25/how-to-fix-home-directory-should-be-accesible-only-by-the-user-warning-message-during-login/
categories:
  - "Tips & How-To's"
tags:
  - linux

---
I just encountered this problem recently so I thought I would drop a short note about it. Once I was trying to mount ext3 filesystems with read and write support and I, by mistake, did chmod my entire root partition as 775.

In this process, I made a warning message appear everytime I login, saying something like the home directory should be accessible by only its owner and should be set to 644. In addition, it also said that the file "$HOME/.dmrc" should be blah blah blah.

First, I made my home directory into 644. Then it won't let me login saying it was not able to access my home directory. If I set it to 755 then that damn warning message I mentioned earlier reappears (What do I do?). Then what i doubted was that ".dmrc" file.

<span style="#888888;"><strong>WHAT TO DO?</strong></span>

I just **set the permission of "$HOME/.dmrc" to 644** , **leaving rest to be in775** and **it worked like a charm**. I now am able to login and no warning message appears.

I hope this will help you too.

_[Editors note: Here's a good example of why you should not mess with user permissions and chmod/chown commands if you have no idea what they do]_

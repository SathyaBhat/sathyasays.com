---
title: Free Software Easter Eggs
author: Sathya
type: post
date: 2008-02-21T04:25:10+00:00
url: /2008/02/21/free-software-easter-eggs/
categories:
  - General
tags:
  - apt-get
  - Arch
  - bin
  - DE
  - easter eggs
  - free
  - free software
  - fun
  - Human
  - humour
  - install
  - linux
  - magazine
  - personal
  - read
  - repo
  - rm
  - show
  - software
  - sudo
  - Super
  - tar
  - terminal
  - Ubuntu
  - ux
  - X

---
 The good folks over at [Free Software Magazine][1] got bored writing regular articles on free software. For some chuckles, they decided to research on some easter eggs. Here&#8217;s what they found.

What is it with cows and GNU/Linux? Let me answer my own self-serving question and show you some varied and slightly bizarre examples of human randomness. Assuming you are running under Ubuntu from a terminal type:

<pre>apt-get help | grep -i super

This APT has Super Cow Powers.</pre>

OK, let us generate some somewhat warped and deranged ASCII

<pre>apt-get moo
         (__)
         (oo)
   /------\/
  / |    ||
 *  /\---/\
    ~~   ~~
...."Have you mooed today?"...</pre>

Having fun yet? My brain is starting to bake trying to work out the meaning of it all. There are even serious and well researched Ubuntu [bug reports][2] on the subject.

How about trying to use aptitude from the command line to discern a recognizable and potentially disturbing pattern of social humor. Can we get aptitude to talk sense? Let us beat it around the head verbally and see if we can get it to admit its origins.

<pre>aptitude -v moo
There really are no Easter Eggs in this program.
aptitude -vv moo
Didn't I already tell you that there are no Easter Eggs in this program?
aptitude -vvv moo
Stop it!
aptitude -vvvv moo
Okay, okay, if I give you an Easter Egg, will you go away?
aptitude -vvvvv moo
All right, you win.

                               /----\
                       -------/      \
                      /               \
                     /                |
   -----------------/                  --------\
   ----------------------------------------------
 aptitude -vvvvvv moo

What is it?  It's an elephant being eaten by a snake, of course.</pre>

Yes now I understand life clearly. Well, if you cannot beat them with sharp pointy objects, then join them I say. Let me introduce to a small program called cowsay, a man’s best friend, a configurable talking cow. Just what you need when you already have multiple personalities and two children. From your favourite terminal, please type:

<pre>sudo apt-get install cowsay
cowsay what the

 ----------
  what the
 ----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w||
                ||     ||</pre>

Cows, cows everywhere and not a pint of milk to drink.

For more chuckles, read the entire article over at [Free Software Magazine][3]

 [1]: http://www.freesoftwaremagazine.com
 [2]: https://launchpad.net/ubuntu/+source/apt/+bug/56125
 [3]: http://www.freesoftwaremagazine.com/articles/free_software_easter_eggs/
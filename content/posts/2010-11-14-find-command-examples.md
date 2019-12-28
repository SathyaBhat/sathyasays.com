---
title: find command examples
author: Sathya
type: post
date: 2010-11-14T03:37:52+00:00
url: /2010/11/14/find-command-examples/
topsy_short_url:
  - http://u.sbhat.me/brNgVD
categories:
  - "Tips &amp; How-To's"
tags:
  - applications
  - bin
  - blog
  - cat
  - chm
  - commands
  - DE
  - delete
  - Desktop
  - download
  - DVD
  - exe
  - file
  - find
  - Home
  - IM
  - iso
  - linux
  - login
  - move
  - music
  - os
  - PHP
  - preview
  - record
  - review
  - rm
  - security
  - tar
  - "tips-and-howto's"
  - TV
  - Ubuntu
  - UNIX
  - usb
  - user
  - ux
  - write
  - X

---
I&#8217;ve used find extensively and always wanted to writeup a nice post on this, but the linked post trumps my effort! Copy pasted from his blog, as the person&#8217;s allowed to do so. Also, as a general note &#8211; before using exec with the actual command, do preview it!

`<br />
------------------------------------------------------------------------------------------<br />
remove empty directories<br />
------------------------------------------------------------------------------------------<br />
# find . -depth -type d -empty -exec rmdir {} \;`

`<br />
------------------------------------------------------------------------------------------<br />
change various file attributes<br />
------------------------------------------------------------------------------------------<br />
# find . -type f -exec chgrp users {} \;<br />
# find . -type f -exec chmod 644 {} \;<br />
# find . -type d -exec chmod 755 {} \;`

`<br />
------------------------------------------------------------------------------------------<br />
find all 'iso' files (case insensitive)<br />
------------------------------------------------------------------------------------------<br />
find -iname '*.iso'`

`example output:<br />
./Documents/ubuntu-10.04.1-server-i386.iso<br />
./photos.iso<br />
./pauls_wedding_video.iso<br />
./CentOS-5.3-i386-bin-DVD/CentOS-5.3-i386-bin-DVD.iso</p>
<p>------------------------------------------------------------------------------------------<br />
Find all the file with the name 'ruby' in them. (starts in the current directory)<br />
Note:<br />
-name is case sensitive<br />
-iname is insensitve<br />
------------------------------------------------------------------------------------------<br />
# find -name ruby</p>
<p>example output:<br />
./Download/jruby-1.1.5/lib/ruby<br />
./.gem/ruby</p>
<p>------------------------------------------------------------------------------------------<br />
find all the pdf files > 10M and list their details<br />
Note: {} stands for the file name, \; terminates the command<br />
(the output below is little ugly because of word-wrap)<br />
------------------------------------------------------------------------------------------<br />
# find . -iname '*.pdf' -and -size +10M -exec ls -l {} \;</p>
<p>example output:<br />
-rw-rw-r-- 1 chuck chuck 11173003 2008-11-07 06:14 ./Desktop/SecurityPlus.PDF<br />
-rw-rw-r-- 1 chuck chuck 12857446 2009-04-17 13:55 ./Documents/RoR/Railspace/Railspace.pdf<br />
-rw-rw-r-- 1 chuck chuck 12894140 2009-08-18 15:01 ./Documents/Calculus, Applications and Theory.pdf<br />
-rw-rw-r-- 1 chuck chuck 29461154 2009-10-10 17:13 ./Documents/PDF's/Learning the vi and Vim Editors, 7th Edition.pdf<br />
-rw-rw-r-- 1 chuck chuck 12857446 2009-04-17 13:55 ./Documents/PDF's/Railspace.pdf</p>
<p>------------------------------------------------------------------------------------------<br />
find all txt files in current directory that contain "ruby"<br />
------------------------------------------------------------------------------------------<br />
find . -iname "*.txt" -print0 |xargs -0 grep ruby</p>
<p>------------------------------------------------------------------------------------------<br />
find all php files in current and sup-directories that contain "legend". list names only.<br />
------------------------------------------------------------------------------------------<br />
find . -iname '*.php' -exec grep -l "legend" {} \;</p>
<p>example output:<br />
./login.php<br />
./includes/customer_form.html.php<br />
./customers/form.html.php<br />
./customers/orginal_form.html.php<br />
./customer_record2.php</p>
<p>------------------------------------------------------------------------------------------<br />
find all subdirs and set excutiable bit:<br />
Note: {} stands for the file name, \; terminates the command<br />
------------------------------------------------------------------------------------------<br />
find * -type d -exec chmod a+x {} \;</p>
<p>------------------------------------------------------------------------------------------<br />
find all extentions in subdirectories<br />
------------------------------------------------------------------------------------------<br />
find . -type f | sed -e 's/.*\.//' | sort | uniq -c | sort -rn</p>
<p>example output:<br />
10 htm<br />
7 jpg<br />
4 gif<br />
1 css</p>
<p>------------------------------------------------------------------------------------------<br />
change extension of all files from .html to .htm in all subdirectoies<br />
------------------------------------------------------------------------------------------<br />
find . -iname "*.html" | xargs rename .html .htm {} \;</p>
<p>------------------------------------------------------------------------------------------<br />
fix file permissions (e.g. after copy from usbdrive)<br />
------------------------------------------------------------------------------------------<br />
find . -type d -exec chmod 775 {} \;<br />
find . -type f -exec chmod 664 {} \;</p>
<p>example output:<br />
drwxrwxr-x 2 chuck chuck 4096 2010-05-05 10:21 my_directory/<br />
-rw-rw-r-- 1 chuck chuck 300 2010-05-07 18:14 my_file.txt</p>
<p>------------------------------------------------------------------------------------------<br />
find all the *.ini files in home directory but ignore hidden directories<br />
(note: -print needed to print. not sure why. maybe because of the "or" (-o)<br />
------------------------------------------------------------------------------------------<br />
find ~/ -type d -name "*.*" -prune -o -iname "*.ini" -print</p>
<p>------------------------------------------------------------------------------------------<br />
find all *.ico files on computer but ignore directories named "win7", "share", "doc"<br />
(note: -print is important on this. see above)<br />
------------------------------------------------------------------------------------------<br />
find / -type d \( -name win7 -o -name share -o -name doc \) -prune -o -iname "*.ico" -print</p>
<p>`

`------------------------------------------------------------------------------------------<br />
delete all files like 'my_music_file 1.m4a'<br />
------------------------------------------------------------------------------------------<br />
find . -iname '* 1.m4a' -exec rm {} \;<br />
` 

[Linux/Unix CLI “find” examples. « Useless Posts from Tigard][1].

 [1]: http://chuck97224.wordpress.com/2010/11/13/linuxunix-cli-find-examples/
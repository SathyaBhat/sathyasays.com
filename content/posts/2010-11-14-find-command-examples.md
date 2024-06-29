---
title: find command examples
author: Sathyajith Bhat
type: post
date: 2010-11-14T03:37:52+00:00
url: /2010/11/14/find-command-examples/

categories:
  - "Tips & How-To's"
tags:
  - applications
  - linux
  - ubuntu

---

I've used find extensively and always wanted to writeup a nice post on this, but the linked post trumps my effort! Copy pasted from his blog, as the person's allowed to do so. Also, as a general note - before using exec with the actual command, do preview it!


### remove empty directories

```
# find . -depth -type d -empty -exec rmdir {} \;
```

change various file attributes

```
# find . -type f -exec chgrp users {} \;
# find . -type f -exec chmod 644 {} \;
# find . -type d -exec chmod 755 {} \;
```


### find all 'iso' files (case insensitive)

```
find -iname '*.iso'

example output:
./Documents/ubuntu-10.04.1-server-i386.iso
./photos.iso
./pauls_wedding_video.iso
./CentOS-5.3-i386-bin-DVD/CentOS-5.3-i386-bin-DVD.iso
```

### Find all the file with the name 'ruby' in them. (starts in the current directory)

Note:

* `-name` is case sensitive
* `-iname` is insensitve

```
# find -name ruby

example output:
./Download/jruby-1.1.5/lib/ruby
./.gem/ruby
```


### find all the pdf files > 10M and list their details


Note: `{}` stands for the file name, `\;` terminates the command

```
# find . -iname '*.pdf' -and -size +10M -exec ls -l {} \;

example output:
-rw-rw-r-- 1 chuck chuck 11173003 2008-11-07 06:14 ./Desktop/SecurityPlus.PDF
-rw-rw-r-- 1 chuck chuck 12857446 2009-04-17 13:55 ./Documents/RoR/Railspace/Railspace.pdf
-rw-rw-r-- 1 chuck chuck 12894140 2009-08-18 15:01 ./Documents/Calculus, Applications and Theory.pdf
-rw-rw-r-- 1 chuck chuck 29461154 2009-10-10 17:13 ./Documents/PDF's/Learning the vi and Vim Editors, 7th Edition.pdf
-rw-rw-r-- 1 chuck chuck 12857446 2009-04-17 13:55 ./Documents/PDF's/Railspace.pdf
```

### find all txt files in current directory that contain "ruby"

```
find . -iname "*.txt" -print0 |xargs -0 grep ruby
```

###  find all php files in current and sup-directories that contain "legend". list names only.

```
find . -iname '*.php' -exec grep -l "legend" {} \;

example output:
./login.php
./includes/customer_form.html.php
./customers/form.html.php
./customers/orginal_form.html.php
./customer_record2.php
```

### find all subdirs and set excutiable bit:

Note: {} stands for the file name, \; terminates the command

```
find * -type d -exec chmod a+x {} \;
```

### find all extentions in subdirectories

```
find . -type f | sed -e 's/.*\.//' | sort | uniq -c | sort -rn

example output:
10 htm
7 jpg
4 gif
1 css
```

### change extension of all files from .html to .htm in all subdirectoies

```
find . -iname "*.html" | xargs rename .html .htm {} \;
```

### fix file permissions (e.g. after copy from usbdrive)

```
find . -type d -exec chmod 775 {} \;
find . -type f -exec chmod 664 {} \;

example output:
drwxrwxr-x 2 chuck chuck 4096 2010-05-05 10:21 my_directory/
-rw-rw-r-- 1 chuck chuck 300 2010-05-07 18:14 my_file.txt
```

### find all the *.ini files in home directory but ignore hidden directories

```
note: -print needed to print. not sure why. maybe because of the "or" (-o)

find ~/ -type d -name "*.*" -prune -o -iname "*.ini" -print
```

```
find all *.ico files on computer but ignore directories named "win7", "share", "doc"
(note: -print is important on this. see above)

find / -type d \( -name win7 -o -name share -o -name doc \) -prune -o -iname "*.ico" -print
```

### delete all files like 'my_music_file 1.m4a'

```
find . -iname '* 1.m4a' -exec rm {} \;
```

[Linux/Unix CLI “find” examples. « Useless Posts from Tigard][1].

 [1]: https://chuck97224.wordpress.com/2010/11/13/linuxunix-cli-find-examples/

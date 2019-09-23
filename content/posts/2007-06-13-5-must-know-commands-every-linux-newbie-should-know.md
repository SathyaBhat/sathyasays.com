---
title: 5 Commands Every Linux Newbie Must Know
author: Sathya
type: post
date: 2007-06-13T07:25:38+00:00
url: /2007/06/13/5-must-know-commands-every-linux-newbie-should-know/
categories:
  - "Tips &amp; How-To's"
tags:
  - commands
  - tips
  - tutorials
 

---
Although Linux had progressed far from being a command-line only OS to a full fledged totally GUI based one, sometimes, the command line is the best way to get something done. Here are 5 of the must-know commands. These commands can b quite useful and handy.

1: **mount**: Used for mounting Windows/Other partitions, just in case it isn&#8217;t automatically mounted.

Usage:

> **mount <device> <mount-point>**

here <device> refers to the special device where your partitions are.
  
Rather than referring to partitions as drive letters as Windows, every partition in Linux is indicated by a special device. For eg in case if IDE(parallel ATA drives) the Primary master will be /dev/hda and the primary partition will be /dev/hda1(Windows C:) and the logical partitions will be /dev/hda5, /dev/hda6 and so on(for Windows D:, E:.. so on).

<mount-point> indicates to which directory you want the partition to be available as.

Please note that mount command requires root privileges, so run the command as sudo ie,
  
sudo mount <device> <mount-point>

Eg: If you wish to mount the Windows C partition to a /windows/C the command will be,sudo mount /dev/hda1 /windows/C

For SATA drives, the &#8220;hdx&#8221; will be replaced by &#8220;sdx&#8221; ie, instead of /dev/hda1

it&#8217;ll be /dev/sda1

2: **tar/bzip2/bunzip2**: For extracting archives, this command is useful for extracting to directories other than the home directory, where root privileges are required

Usage:
  
(i) For GZipped files(.tar.gz extension)

>  **tar xvfz <archive-name>**

Eg: If the archive name is some-file.tar.gz, then the command will be

> tar xvfz some-file.tar.gz

(ii)For Bzipped files (.tar.bz2 extension)

First, unzip the archive using

> **bunzip2 <archive-name>**

Then untar using the command

>  **tar xvf <archive-name>** 

Eg: If the archive is some-file.tar.bz2 then first unzip it using

bunzip some-file.tar.bz2

You&#8217;ll get the file some-file.tar. Next untar it using

tar xvf some-file.tar

3. **rpm/dpkg** &#8211; Install/Upgrade/Remove RPM/Debian Packages

Usage:

(i) Installing new packages

>  **rpm -ivh <package-name.rpm>**

>  **dpkg -i <package-name.deb>**

(ii) Upgrade existing packages

>  **rpm -Uvh <package-name.rpm>**
> 
>  **dpkg -i <package-name.deb>**

(iii) Removing existing packages

> **rpm -e <package-name>**
> 
>  **dpkg -r <package-name>** 

Note that these commands are suited for individual commands, whose dependencies are met. For complex packages, having many dependencies it&#8217;s better to use apt-get/smart.

For smart: **smart install <package-name>**

For apt-get: **apt-get install <package-name>**

Again these commands require root privileges, so prefix sudo before each of these commands.

4. **cat** &#8211; Concatenate files and print on the standard output. Useful for viewing short text files, logs without having to open any editors

Usage:

> **cat /path/to/file**

Eg: cat /var/log/syslog

If the text file is lengthy, pipe it via more to scroll ie

> **cat /path/to/file |more**

Eg: cat /var/log/syslog |more

5. **dmesg** &#8211; The program helps users to print out their bootup messages. Instead of copying the messages by hand, the user need only:

>  **dmesg > boot.message**s

and mail the boot.messages file to whoever can debug their problem.

**dmesg |tail** Outputs only the last part of dmesg, and is useful to identify any errors, which occured, say if a removable drive is inserted.

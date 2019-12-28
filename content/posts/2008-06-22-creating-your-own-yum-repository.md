---
title: Creating Your Own YUM Repository
author: Sathya
type: post
date: 2008-06-22T15:56:05+00:00
url: /2008/06/22/creating-your-own-yum-repository/
categories:
  - "Tips &amp; How-To's"
tags:
  - Arch
  - cat
  - commands
  - DE
  - distro
  - DVD
  - Fedora
  - file
  - find
  - free
  - hard disk
  - how-tos
  - IM
  - indic
  - install
  - linux
  - mount
  - move
  - net
  - open source
  - Opera
  - os
  - RedHat
  - repo
  - repos
  - repositories
  - repository
  - RHEL
  - RIA
  - rm
  - rpm
  - software
  - support
  - tar
  - tips
  - "tips-and-howto's"
  - tutorials
  - update
  - user
  - ux
  - X
  - yum

---
This is a guest post by <a href="https://tech-nologic.info/" target="_blank"><strong>Kunal Gautam</strong></a>. This article is aimed at RHEL and Fedora users.

If you’ve been using Linux for a while, then you’d know how much of a pain it is to install a software which runs into dependency problems. One way of getting around this is to use a repository.

### What is YUM?

YUM or Yellowdog Updater Modified is an interactive, automated update program which can be used for maintaining system using rpm. Yum is an automatic updater and package installer/remover for rpm systems. It automatically computes dependencies and figures out what things should occur to install packages.
  
Yum makes it easier to maintain groups of machines without having to manually update each one using rpm.

<!--more-->

**What is a Repository ?**
  
A repository is a collection of list of rpm[s]. It contain various information regarding the rpm like its dependencies etc

**Why to use Yum if I can install RPM using rpm command?**
  
Well if you want to install RPM you have to make sure that its dependencies are also installed . But this is not in the case of YUM you can simply install package with its dependencies. YUM take care of your all install things . Also update feature is not available in the rpm installation method but it is available in yum.

**Here are some key features of “Yum”:**

  * Multiple Repositories
  * Simple config file
  * Correct dependency calculation
  * Fast operation
  * rpm-consistent behavior
  * comps.xml group support, including multiple repository groups
  * Simple interface

## **Starting With Creating Your Own Repository [Server Side Configuration]**

### **Step One: Check Prequisites**

  * Have Your Distro CD/DVD
  * Check if you have free space on your Hard Disk or not [Total space required vary from Distro to Distro]

### **Step Two : Copy Disc to Hard Disk**

First mount your CD/DVD  and copy it to hard disk
  
`cp –avr /cd/dvd/mount/point/   /destination/directory/`

Repeat this step with your all your cds .
  
_Note:- If you want install Repository on your network thrugh ftp or http upload in their respective default directories i.e /var/ftp/pub for ftp server and /var/www/html for http server._

### **Step Three : Intalling CreateRepo Package**

Now go to your directory where you copied the files and search for createrepo-\*.rpm file \* may be different from version to version and system architecture
  
Install that rpm using rpm command, as follows

> `rpm -ivh --aid createrepo-*.rpm`

### **Step Four: Run createrepo**

Go to the directory where you copied the file and run the createrepo command

> `createrepo -v .`

**[please note that “.” {dot} after that command as we are in present directory ]**

The server side settings are done.
  
Lets have a look at client side setting now.

## Client Side Setting For YUM

Create a repo file in /etc/yum.repos.d/ directory [ you can name anything to your file make sure a .repo extension is added later on]

> `vim /etc/yum.repos.d/my.repo`

Add following date in that file

> [Myrepo]
  
> name=Any name you want to put
  
> baseurl=file:///destination/directory/
  
> enabled=1
  
> gpgcheck=0

The first line is alias given for your repository . This help to indicate/find that from which repository the package is available.
  
Second line is name for your repo, which you can put anything
  
Next comes baseurl
  
baseurl supports different protocols like file:// ftp:// httpd:// etc. If you are running repository from local system then give absolute path after file:// .
  
For ftp give `ftp://server_ip_or_domain/pub_dir_or_accessable_dir` or `https://server_ip_or_domain/dir`
  
Next line is enabled this specifies if yum should enable that repo server for installation or not 1 is for enable and 0 is for disable
  
gpgcheck is for checking gpg key. As I didn’t require the key-checking feature, I have disabled this. If you have enabled it, then you will have to add one more line after that,

> `gpgkey=/your/path/to/key`

which specifies the location to the gpgkey

After this save that repo file and run following command

> `yum clean all` [ will clean yum database ]
  
> `yum list` [will list the files / packages available on that directory ]

If you are finding this difficult, or are having some promblems, then please feel free to ask your query by dropping a comment.

_Note 1:- SElinux or Firewall may conflict sometimes [ for ftp and http service ]_
  
_Note2 :- I have used RHEL server 5 edition . This process is same for RHEL 4, 5 or for Fedora._

<div id="scid:0767317B-992E-4b12-91E0-4F059A8CECA8:4a3b7185-3a41-47d3-901e-b711508c4443" class="wlWriterSmartContent" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px">
  Technorati Tags: <a rel="tag" href="https://technorati.com/tags/sathya">sathya</a>,<a rel="tag" href="https://technorati.com/tags/sathyasays.com">sathyasays.com</a>,<a rel="tag" href="https://technorati.com/tags/linux">linux</a>,<a rel="tag" href="https://technorati.com/tags/opensource">opensource</a>,<a rel="tag" href="https://technorati.com/tags/RedHat">RedHat</a>,<a rel="tag" href="https://technorati.com/tags/RHEL">RHEL</a>,<a rel="tag" href="https://technorati.com/tags/yum">yum</a>,<a rel="tag" href="https://technorati.com/tags/repo">repo</a>,<a rel="tag" href="https://technorati.com/tags/repository">repository</a>,<a rel="tag" href="https://technorati.com/tags/commands">commands</a>,<a rel="tag" href="https://technorati.com/tags/tips+and+how-tos">tips and how-tos</a>,<a rel="tag" href="https://technorati.com/tags/tutorials">tutorials</a>
</div>

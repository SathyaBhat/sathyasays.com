---
title: Linux Install Guide For Newbies
author: Sathya
type: post
date: 2007-10-31T03:15:45+00:00
url: /2007/10/31/linux-install-guide-for-newbies/
categories:
  - News
tags:
  - /dev
  - AIR
  - boot
  - DE
  - distro
  - DVD
  - ext3
  - file
  - formatting
  - forums
  - git
  - guide
  - hard disk
  - IM
  - install
  - keyboard
  - linux
  - LV
  - mount
  - mounting
  - move
  - music
  - New
  - newbie
  - notes
  - NTFS
  - Opera
  - Operating System
  - operating systems
  - os
  - partition
  - partitioning
  - Partitions
  - read
  - rm
  - RMS
  - root
  - Screen
  - show
  - software
  - tar
  - upgrade
  - user
  - ux
  - Vista
  - windows
  - write
  - X
  - xp

---
<span class="postbody">This excellent Linux installation guide was written by my friend, &#8220;The Trojan&#8221; initially on the CHIP forums. So all credits to him, for writing this excellent post(and note that I&#8217;ve taken his permission to reproduce it here). </span>

 <span class="postbody">I am writing this down considering the fact that most of the newbies who want to try out Linux or want to make a shift to it or want to use it along side with Windows are afraid of the installation and the &#8220;GEEK&#8221; status of the Linux OS. I will try to resolve the issues with both the mental fear of geek status of Linux and the small technical fear of a new operating system.</span>

First with the mental fear as it is necessary that you are mentally ready to do something before actually trying it out! So, what is the reason people fear that Linux is tough to use. Well, Linux is not tough to use, its only that it is a bit more difficult to <span style="font-weight: bold">administer </span> it when compared to Windows Operating systems. So first of all, before installing Linux, be ready that you will have to learn new things and some really interesting facts about the real potential of your hardware and its details will be shown to you. The rules of Linux are much different from that of Windows. But there is <span style="font-weight: bold">JUST NO NEED TO BE AFRAID OF LINUX</span>. It will become easier as you keep on using it.

<!--more-->

So let us start with how to install it. I will compare the Windows XP installation by the side so that it is easier to understand and be prepared while installing Linux. Another thing which I want to clarify is that for people completely new to Linux (or installation procedures of Linux), it is advised that they do backup all their important stuff before trying to install Linux as they may end with no data on the system in case they do something wrong.

OK, so let us step by step:

<span style="color: darkblue"><span style="font-weight: bold"><span style="font-size: 18px; line-height: normal">Step 1</span></span></span>: What is the first step in the installation of Windows XP? Simple, you just put the installation [bootable] CD inside and boot from it. This step is same in Linux as well. You have to put the installation CD/DVD into the tray and boot from it.

<span style="color: darkblue"><span style="font-weight: bold"><span style="font-size: 18px; line-height: normal">Step 2</span></span></span>: Windows XP will load some files/components which will be used to create the environment (the blue screen) where you will take steps to install Windows XP. Similarly a Linux installer will detect your hardware and load the files that will create an installation environment.

The one thing that is different from Windows XP here is that Windows installation environment uses just keyboard whereas i Linux, most distributions will allow you to use Mouse you install Linux.

<span style="color: darkblue"><span style="font-weight: bold"><span style="font-size: 18px; line-height: normal">Step 3</span></span></span>: Now, Linux installer will ask you for date, time and the region where you belong and the language to be selected. This is a small step that Windows setup does towards the end of installation. This step is very simple.

<span style="color: darkblue"><span style="font-weight: bold"><span style="font-size: 18px; line-height: normal">Step 4</span></span></span> So what does Windows do afterwards? It asks you if you want to repair an installation or you want to install a new copy. In linux, it depends on the Linux distribution. Most of the Linux distributions would not ask you if you want to repair. However some of them may show an &#8216;upgrade&#8217; option which will also repair the last installation if it is the same distro and the same version of Linux that was previously installed. This is similar to XP as you cannot repair a Windows Vista or Windows 2000 form a XP CD. So we choose to perform a new installation.

<span style="color: darkblue"><span style="font-weight: bold"><span style="font-size: 18px; line-height: normal">Step 5</span></span></span>: Windows will ask you to perform the partitioning of the hard disk. This is the tough task and it is necessary that the background is clarified about the partitioning and the related terminology before we proceed further. So I am going to write down the related terms , their meanings and other details in a QUOTE box:

<table align="center" border="0" cellpadding="3" cellspacing="1" width="90%">
  <tr>
    <td>
      <span class="genmed"><strong>Quote:</strong></span>
    </td>
  </tr>
  
  <tr>
    <td class="quote">
      There are terms which are related to the Linux world and are unknown to newbies. They must be known because while installations, the setup will ask questions related to it. Let us start:1. <span style="font-weight: bold"><span style="font-style: italic">Partitions (and the names by which they are represented)</span></span>: It is very well known to the Windows users as well. Of course, making partitions helps in managing and organizing data. Windows uses the names C, D, E ,. . . and so on. But Linux does not. and this is the place where a newbie first starts thinking that he made a mistake by putting in the CD and even thinking to install it. I thought the same way but I did not look back and went on. After almost 20 times formatting my hard disk, I knew how it all works and how the disks are names and what everything means. So let me tell you how it is named which will then help us understand how it WORKS.Windows uses alphabets like C and D to make it easy but the Linux way is different as is easier while providing more information than Windows installer. Linux would call the disks as either <span style="text-decoration: underline">/dev/sda</span> or <span style="text-decoration: underline">/dev/sda2</span> (or sometimes just <span style="text-decoration: underline">/sda1</span> or <span style="text-decoration: underline">/sda2</span>) or <span style="text-decoration: underline">/dev/hda1</span> or /<span style="text-decoration: underline">dev/hda2</span> (or sometimes just <span style="text-decoration: underline">/hda1</span> or <span style="text-decoration: underline">/hda2</span>).</p> 
      
      <p>
        How do these stupid names provide information and are easier than Windows. See /dev/sda1 can be divided into 4 parts:<br /> * <span style="font-weight: bold">/dev/</span> : This denotes that the string following it (sda1) is a DEVICE (hence the word &#8216;dev&#8217;).
      </p>
      
      <p>
        * <span style="font-weight: bold">sd</span> OR <span style="font-weight: bold">hd</span> : The letter &#8216;s&#8217; stands for &#8216;SCSI&#8217; devcies. Do not bang your head on what SCSI is. Just think that it would show SATA devices. MOST of the new hard disks are SATA. So &#8216;sd&#8217; would mean that it is referring to the hard disk.
      </p>
      
      <p>
        The letters &#8216;hd&#8217; refer to the IDE devices such as your DVD writer or a Hard disk connectd to the IDE cable (looks like a long ribbon).
      </p>
      
      <p>
        * <span style="font-weight: bold">a</span> : This represents the &#8216;number&#8217; of hard disk. For example, if you have 2 hard disks, it will be shown as &#8216;b&#8217; for the second disk and the hard disk itself will be represented by /dev/sdb.
      </p>
      
      <p>
        * <span style="font-weight: bold">1</span> : This is the partition number on the hard disk. Say you have three partitions on your first hard disk. Then the three partitions will be represented by /dev/sda1 , /dev/sda2/ and /dev/sda3. Your DVD Drive will appear as /dev/hda
      </p>
      
      <p>
        So for example I am giving some names which would help you understand the nomenclature. Do understand this coz if you mess up with the partitions, you will end up with something you never wanted!
      </p>
      
      <p>
        e.g.:
      </p>
      
      <p>
        /dev/sda3 : The third partition (digit 3 at end) on the first (the letter &#8216;a&#8217;) hard disk (signified by &#8216;sd&#8217;) of our system
      </p>
      
      <p>
        /dev/sdb2 : The 2nd (digit &#8216;2&#8217; at the end) on the second (the letter &#8216;b&#8217;) hard disk of your system
      </p>
      
      <p>
        /dev/hda : The IDE device of the system.
      </p>
      
      <p>
        If you have 2 IDE devices, they will show up as hda1 and hda2.
      </p>
      
      <p>
        EDIT: With the newer kernel, at boot time all hard disks will shown as /dev/sdx, correct me if I&#8217;m wrong<br /> <span style="font-weight: bold"><span style="font-size: 18px; line-height: normal">NOTE:</span></span>
      </p>
      
      <table align="center" border="0" cellpadding="3" cellspacing="1" width="90%">
        <tr>
          <td>
            <span class="genmed"><strong>Code:</strong></span>
          </td>
        </tr>
        
        <tr>
          <td class="code">
            1> It is very much advisable that before formatting or resizing any partition on Windows, you first give some name to the partitions in Windows XP (such as &#8216;DATA&#8217; or &#8216;MUSIC&#8217; or &#8216;DOCS&#8217; or something similar so that if you forget, the name may come to help. Also try to move all data to one single partition so that when resizing partitions, you do not face difficulties.2> Sometimes, the numbering of sda1 or sda5 may be confusing. In that case, remember the order in which the partitioning has been done and write it on the piece of paper. For example, if you have 3 partitions of 30, 20 and 10 GB size respectively then you can easily write it down on paper, and see the name assigned by Linux and match it with the drive number you have already written! That will help you.
          </td>
        </tr>
      </table>
      
      <p>
        <span class="postbody"></span>
      </p>
      
      <p>
        2. <span style="font-weight: bold"><span style="font-style: italic">File systems</span></span>: File Systems are a way of keeping the data on the disk. File systems differ from one Operating System to other because their design differs. So Linux uses files systems that are different from Windows. Some of the file systems are : etx2, etx3, reiserfs, jfs, xfs etc. So you will have to format the partition on which you want to install Linux with one of them. etx3 is recommended as it is very stable and there is a software available to help you access data on ext3 which will mean that you will be able to access your Linux documents from Windows.
      </p>
      
      <p>
        3. <span style="font-weight: bold"><span style="font-style: italic">Mount Points</span></span>: Mount points are a bit confusing but after you understand it, It is so easy that you will love Linux for the simple way to allow you to mount the partitions on it. Mount points are certain directories (or folders) where whole partition appears to be kept. To understand mount point, do the following on a Windows XP system:<br /> <span style="color: blue"><br /> 1> Go to Start ==> Run and type &#8216;compmgmt.msc&#8217; and press [enter].<br /> 2> On the left side select &#8220;Disk Management&#8221;. On the right side the hard disk partitions will appear. Right click on any NTFS formatted drive and choose &#8220;add or change drive letter and paths&#8221;.<br /> 3> Now click on add. Select &#8220;mount drive in an empty NTFS folder&#8221;.<br /> 4> Now select an empty folder on a NTFS drive. and click on OK. </span>
      </p>
      
      <p>
        Now you will see that all the contents that were there in that drive appears to be there in the folder that you had chosen. What you just saw is called mounting. You have mounted a drive a folder. Similar thing happens with Linux.
      </p>
      
      <p>
        Its just another matter that when you are using Windows, mounting a drive into a folder is a choice; on Linux it is a necessity that for using a partition, it must be mounted into a folder (a directory). So when you install Linux, pay attention to what partitions are being used for what. The &#8216;/&#8217; mount point means that all the system files will be kept here. It is necessary that a &#8216;/&#8217; mount point exists. You can also make your Windows drives mount by creating a folder and using it as a mount point.</td> </tr> </table> 
        
        <p>
          <span class="postbody"></span>
        </p>
        
        <p>
          So after you have done the partitioning, you need to create mount points where your drives will be accessed as directories. After you have done that, you may choose to change the software settings (if your Linux installer permits you to)
        </p>
        
        <p>
          <span style="color: darkblue"><span style="font-weight: bold"><span style="font-size: 18px; line-height: normal">Step 6</span></span></span> You may like to change the boot loader settings. However it is not recommended to mess around with the boot loader thing. In most of the cases, default settings will work fine.
        </p>
        
        <p>
          <span style="color: darkblue"><span style="font-weight: bold"><span style="font-size: 18px; line-height: normal">Step 7</span></span></span>: Start the install. It will automatically complete<br /> <span style="color: darkblue"><span style="font-weight: bold"><span style="font-size: 18px; line-height: normal">Step 8</span></span></span>: After the install is complete, the system may or may not reboot. Now it will ask you to enter the &#8220;root password&#8221;. The &#8216;root&#8217; is the &#8220;administrator&#8221; account of Linux. Enter a password and remember that you do not forget what you are typing as there are nothing like password hints which will help you remind the password. Without this password, you will end up with almost a locked system. So do take care that you enter a password which you will never forget.
        </p>
        
        <p>
          Now it will ask you to create other user accounts. Do that and finish the install. One thing to be remembered that all that you enter is <span style="font-weight: bold">CaSe SeNsiTiVe</span>. So be careful.
        </p>
        
        <p>
          <span style="font-size: 18px; line-height: normal"><span style="font-weight: bold">Step 9</span></span>: Enjoy! Linux is installed!
        </p>
        
        <p>
          <span style="font-size: 18px; line-height: normal"><span style="color: green"><br /> If you have any queries or are confused, just ask it in the <a href="https://www.sathyasays.com/forums">forums</a></span> </span>
        </p>

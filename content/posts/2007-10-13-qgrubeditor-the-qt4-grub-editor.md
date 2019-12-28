---
title: QGRUBEditor – The QT4 GRUB Editor
author: Sathya
type: post
date: 2007-10-13T07:22:39+00:00
url: /2007/10/13/qgrubeditor-the-qt4-grub-editor/
categories:
  - News
tags:
  - apps
  - boot
  - cat
  - console
  - DE
  - delete
  - Desktop
  - file
  - fun
  - grub
  - IM
  - install
  - menu
  - New
  - Opera
  - os
  - Qt
  - rm
  - root
  - script
  - sudo
  - update
  - user
  - warning
  - X
  - xp

---
<font size="2"><strong>Description:</strong><br /> <span class="smallcontenttext">QGRUBEditor is a system tool to view and edit the GRUB boot loader. It offers many features and it is the perfect solution for those who want to change the way GRUB works, without messing with GRUB&#8217;s configuration files.</p> 

<p>
  HOW TO INSTALL:<br /> Install by entering into the extracted folder and typing (in the console)
</p>

<p>
  <strong>qmake-qt4</strong>
</p>

<p>
  <strong>make</strong>
</p>

<p>
  <strong>sudo make install</strong>
</p>

<p>
  For more information see the INSTALL file.
</p>

<p>
  Have fun!</span>
</p>

<p>
  <strong>Changelog:</strong><br /> <span class="smallcontenttext">v.2.1.0<br /> &#8212;&#8212;-<br /> *ADDED: Created a library (which however doesn&#8217;t use pure C++ but relies on Qt4) from the old source code<br /> *ADDED: The first time the application runs it prompts the user about the built-in auto backup feature.<br /> *ADDED: Default Entry is now highlighted and explicitly declared as Default<br /> *ADDED: New setting: the user may select the highlight color<br /> *FIXED: Utilised the at(x) function instead of the [] operator in the vectors to slightly improve speed (only where applicable)<br /> *FIXED: Set icon size spinboxes&#8217; maximum and default to 32<br /> *FIXED: In order to erase the contents of strings, = QString() is utilised instead of = &#8220;&#8221;<br /> *FIXED: Global Context Menu was reimplemented in a different manner<br /> *FIXED: Updated the &#8220;No Root Permissions&#8221; warning message, because QGRUBEditor may not load if you delete one of the 3 files it mentions.<br /> *FIXED: Improved the desktop files<br /> *FIXED: Updated About box&#8217;s description<br /> *FIXED: Did some minor corrections<br /> *I18N: Updated the Greek, French, German, Russian and Ukrainian translations</span>
</p>

<p>
  Get it from <a href="https://www.qt-apps.org/content/show.php/QGRUBEditor?content=60391">QT Apps </a> </font>
</p>

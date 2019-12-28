---
title: 'How To: Rescue Windows Files Using Linux and Python'
author: Sathya
type: post
date: 2007-10-20T04:59:45+00:00
url: /2007/10/20/how-to-rescue-windows-files-using-linux-and-python/
categories:
  - News
tags:
  - bin
  - cat
  - DE
  - file
  - IM
  - install
  - linux
  - media
  - Opera
  - Operating System
  - os
  - script
  - tar
  - ux
  - windows
  - X

---
<span style="font-weight: bold">Problem</span>: Windows Operating System is broken, must be a virus or something; need to rescue important files immediately.<span style="font-weight: bold"></p> 

<p>
  Solution</span>: A Linux Live CD with Python pre-installed; an external storage device; this Python Script:
</p>

<p>
  #!/usr/bin/python<br /> # Filename: backup.py<br /> import os, time
</p>

<p>
  source = [&#8216;DIRECTORY OF WINDOWS FILES TO BE BACKED-UP!’]<br /> target_dir = &#8216;LOCATION OF EXTERNAL STORAGE DEVICE!&#8217;<br /> today = target_dir + time.strftime(&#8216;%Y%m%d&#8217;)<br /> now = time.strftime(&#8216;%H%M%S&#8217;)<br /> comment = raw_input(&#8216;Enter a comment &#8211;> &#8216;)<br /> if len(comment) == 0:<br /> target = today + os.sep + now + &#8216;.zip&#8217;<br /> else:<br /> target = today + os.sep + now + &#8216;_&#8217; + \<br /> comment.replace(&#8216; &#8216;, &#8216;_&#8217;) + &#8216;.zip&#8217;<br /> if not os.path.exists(today):<br /> os.mkdir(today) # make directory<br /> print &#8216;Successfully created directory&#8217;, today<br /> zip_command = &#8220;zip -qr &#8216;%s&#8217; %s&#8221; % (target, &#8216; &#8216;.join(source))
</p>

<p>
  if os.system(zip_command) == 0:<br /> print &#8216;Successful backup to&#8217;, target<br /> else:<br /> print &#8216;Backup FAILED&#8217;
</p>

<p>
   Source: <a href="https://junauza.blogspot.com/2007/10/how-to-rescue-windows-files-using-linux.html">Tech Source From Bohol</a>
</p>

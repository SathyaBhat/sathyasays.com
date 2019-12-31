---
title: 'Statutory warning: Decimals in your logrotate config can be bad for your server’s disk space'
author: Sathya
type: post
date: 2016-12-12T10:15:58+00:00
url: /2016/12/12/statutory-warning-decimals-in-your-logrotate-config-can-be-bad-for-your-servers-disk-space/
categories:
  - "Tips & How-To's"
tags:
  - chef
  - DevOps
  - logrotate
  - ops
  - ruby

---
Last night as I was about to head to sleep, <a href="https://sensuapp.org/" target="_blank">Sensu</a> started emailing me about disk space warnings on one of the backend servers. That's strange, I thought. I had set up <a href="https://github.com/logrotate/logrotate" target="_blank">logrotate</a> with appropriate limits to ensure the log file size is reasonable and rotation happens on a daily basis.

Curious, I ssh'd into the server to investigate. Running a df -h indicated as expected the disk space in use was over 70% (which is the trigger for sensu to send a notification) and the log files had grown way over expected size. So why didn't logrotate rotate the files? I ran logrotate again to see what's happening

`<br />
$ sudo /etc/cron.daily/logrotate<br />
error: backend:7 bad size '536870912.0'<br />
error: found error in "log/production.log", skipping`

Huh, ok so now we know why logrotate didn't run. But having a decimal in the config causes it to flag as bad size? I checked the documentation and <a href="https://www.linuxcommand.org/man_pages/logrotate8.html" target="_blank">it doesn't mention so</a>:

<pre><b>size</b> <i>size</i>
              Log files are rotated when they grow bigger then <i>size</i> bytes.  If
              <i>size</i>  is  followed by <i>M</i>, the size if assumed to be in megabytes.
              If the <i>k</i> is used, the size is in kilobytes. So  <b>size</b>  <b>100</b>,  <i>size</i>
              <i>100k</i>, and <i>size</i> <i>100M</i> are all valid.</pre>

Removing the decimal allowed logrotate to work fine and rotated the files. So that's a TIL for me. In case you're wondering how that decimal came into the picture, <a href="https://www.chef.io/" target="_blank">Chef</a> is used as the CM tool for deploying all changes. The size is defined in a recipe as so

`size (0.5 * (1024 * 1024 * 1024))<br />
maxsize (0.5 * (1024 * 1024 * 1024))`

Now the first number is templated based on what service is being deployed and for the backend, it is configured as 0.5. Since Chef uses Ruby, this evaluates to &#8216;536870912.0' and thus, the error.

---
title: 'Statutory warning: Decimals in your logrotate config can be bad for your server’s disk space'
author: Sathya
type: post
date: 2016-12-12T10:15:58+00:00
url: /2016/12/12/statutory-warning-decimals-in-your-logrotate-config-can-be-bad-for-your-servers-disk-space/
categories:
  - "Tips &amp; How-To's"
tags:
  - chef
  - DevOps
  - logrotate
  - ops
  - ruby

---
Last night as I was about to head to sleep, <a href="https://sensuapp.org/" target="_blank">Sensu</a> started emailing me about disk space warnings on one of the backend servers. That&#8217;s strange, I thought. I had set up <a href="https://github.com/logrotate/logrotate" target="_blank">logrotate</a> with appropriate limits to ensure the log file size is reasonable and rotation happens on a daily basis.

Curious, I ssh&#8217;d into the server to investigate. Running a df -h indicated as expected the disk space in use was over 70% (which is the trigger for sensu to send a notification) and the log files had grown way over expected size. So why didn&#8217;t logrotate rotate the files? I ran logrotate again to see what&#8217;s happening

`<br />
$ sudo /etc/cron.daily/logrotate<br />
error: backend:7 bad size '536870912.0'<br />
error: found error in "log/production.log", skipping`

Huh, ok so now we know why logrotate didn&#8217;t run. But having a decimal in the config causes it to flag as bad size? I checked the documentation and <a href="http://www.linuxcommand.org/man_pages/logrotate8.html" target="_blank">it doesn&#8217;t mention so</a>:

<pre><b>size</b> <i>size</i>
              Log files are rotated when they grow bigger then <i>size</i> bytes.  If
              <i>size</i>  is  followed by <i>M</i>, the size if assumed to be in megabytes.
              If the <i>k</i> is used, the size is in kilobytes. So  <b>size</b>  <b>100</b>,  <i>size</i>
              <i>100k</i>, and <i>size</i> <i>100M</i> are all valid.</pre>

Removing the decimal allowed logrotate to work fine and rotated the files. So that&#8217;s a TIL for me. In case you&#8217;re wondering how that decimal came into the picture, <a href="https://www.chef.io/" target="_blank">Chef</a> is used as the CM tool for deploying all changes. The size is defined in a recipe as so

`size (0.5 * (1024 * 1024 * 1024))<br />
maxsize (0.5 * (1024 * 1024 * 1024))`

Now the first number is templated based on what service is being deployed and for the backend, it is configured as 0.5. Since Chef uses Ruby, this evaluates to &#8216;536870912.0&#8217; and thus, the error.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2016/12/12/statutory-warning-decimals-in-your-logrotate-config-can-be-bad-for-your-servers-disk-space/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1488" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2016/12/12/statutory-warning-decimals-in-your-logrotate-config-can-be-bad-for-your-servers-disk-space/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1488" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2016/12/12/statutory-warning-decimals-in-your-logrotate-config-can-be-bad-for-your-servers-disk-space/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1488" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2016/12/12/statutory-warning-decimals-in-your-logrotate-config-can-be-bad-for-your-servers-disk-space/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2016/12/12/statutory-warning-decimals-in-your-logrotate-config-can-be-bad-for-your-servers-disk-space/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
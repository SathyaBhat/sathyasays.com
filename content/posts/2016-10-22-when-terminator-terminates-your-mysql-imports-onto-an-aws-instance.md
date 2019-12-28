---
title: 'DevOps Diaries: When Terminator terminates your MySQL imports onto an AWS Instance…'
author: Sathya
type: post
date: 2016-10-22T17:11:16+00:00
url: /2016/10/22/when-terminator-terminates-your-mysql-imports-onto-an-aws-instance/
categories:
  - Cloud
tags:
  - Amazon Web Services
  - AWS
  - Database
  - DevOps
  - linux
  - MySQL

---
I have begun to use <a href="https://launchpad.net/terminator" target="_blank">Terminator</a> quite a lot. Terminator&#8217;s quite handy when you want to connect to multiple servers on a single terminal thanks to its split pane feature. (And yes I know about tmux & screen &#8211; I have screen on my servers, don&#8217;t want to get into the headache that is nested screen panes).

Few days back <a href="https://styletag.com" target="_blank">we</a> were preparing for a big migration & deploy and I was tasked upon to prepare a failover just in case the migration goes wrong. I have an automated daily backup from prod and restore to local server, I decided to restore from the MySQL dump on the local server onto the AWS instance via the automated process. Since database restores can take a bit of time, I started the restore and went over to grab some coffee. Once back, I noticed that the import was done and proceeded with a rake db:migrate and realized that rake was doing a migration going all the way back **from the start**&#8230; that did not look proper.

<!--more-->

I connected over to the failover instance and realized only about 60% of the restore was done. First thoughts: oh shit!? Why? How? Are my database backups screwed? Hasn&#8217;t anyone noticed this? How much did I setback our migration timelines?

Not wanting to waste more time, I decided to restore a RDS instance from Amazon&#8217;s snapshots(hey, I guess Amazon would do a better work than me!?), while simultaneously downloading the last dump which my automated process is doing. Some time later, the RDS instance was up and running and the backup download was done. Then I realized that the database dump was about ~400MB gzipped and expanded to about 4.5GB uncompressed. One big ass SQL file &#8211; how the heck do I validate its correctness? For funsies I loaded it up on Sublime.. the loading bar was moving slower than a sloth. No dice. Tried with vim.. yeah same result. My *nix instinct kicked in(while simultaneously facepalming myself for not doing this earlier) and I tried the <a href="https://en.wikipedia.org/wiki/Tail_(Unix)" target="_blank">tail -n 100</a> way. Huh. The dumps are proper. Down to the last table & row. So WTF is causing this to fail!?

I continued to prepare for the migration and half my mind was still on this. Being _slightly obsessive_ about things like these, I decided to restart the import again, this time ditching the automated script and going the &#8220;good ol'&#8221; manual way, and lo & behold, the same thing happened again, though this time at a slightly different time. However, this time I noticed there was an error:

> The error code is 2013: Lost connection to the MySQL server during the query.

error. Hm, why&#8217;s that? There was no Internet connectivity issues and all other metrics seem fine. What could be causing this? I restarted the import again, and again this time the import was killed with the same error. However, this time by chance I noticed the trigger for this error: I had resized Terminator pane. Did you go WTF!? Yeah, same here. Still reeling from this, I tried the same: restarted the import, resized the pane and bam! The restore was killed and connection dropped. Now knowing the cause, the started the import(again!) and went all out to ensure I didn&#8217;t touch the pane and voila, everything went fine.

I enquired with my colleagues if they had seen something like this, and nope no one did. I still haven&#8217;t figured out the reason though. But some takeaways from me:

  * Do your MySQL imports from a separate tab
  * If you still need to use the same tab with a split pane, don&#8217;t touch the pane
  * Make sure you check for return codes for your automated stuff(I suppose this is elementary, well shit)
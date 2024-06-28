---
title: Slimming down my repo using git-filter-repo
author: Sathyajith Bhat
type: post
date: 2023-04-11
url: /2023/04/11/powershell-fzf-psfzf
description: Here's how you can get the goodness of fuzzy search in your PowerShell terminal with fzf.
featured_image: https://i.sathyabh.at/ss/fzf-docker-example.png
meta_image: https://i.sathyabh.at/ss/fzf-docker-example.png
categories:
  - DevOps
  - "Tips & How-To's"
tags:
  - git
  - opensource
draft: true
---
### Why?


### git filter-branch


---
https://github.com/18F/C2/issues/439

git rev-list --objects --all | grep -f <(git verify-pack -v .git/objects/pack/*.idx| sort -k 3 -n | cut -f 1 -d " " | tail -10)
88997e0c2e59b52351d3bccf426d347a14fba2d0 static/img/2017/01/strava.mp4
71bdbd6c98357f2b48cc198289836d40056f47d4 static/img/2018/02/IMG_20180217_095935.jpg
55693d36968f8cfe2b119f584abff8b71dc5c48e static/img/2018/02/IMG_20180217_100051.jpg
cbde5b1c6bd85079a1d7ad88ae3f2c466509f8ef static/img/2018/02/IMG_20180217_100157.jpg
34c3e3653806da957fd64275e352ab727a726eb3 static/img/2018/02/IMG_20180217_100639.jpg
0f4f4fd1bd7bcf781d4864d19051b40149bd6f40 static/img/2018/02/IMG_20180217_100655.jpg
9100d7f722d92104ab55ad138017c974370a57b0 static/img/2018/02/IMG_20180217_104319.jpg
06446a2279805ef567e9e675e4060be6bd1a7c4e static/img/2018/02/IMG_20180217_113038.jpg
9dc7c22dc096a0706bbc912740eca734e86dbaf1 static/img/2018/02/IMG_20180217_120258.jpg
484c29544c42707d0b6355e38f1b005ad3225fb7 static/img/hellforge-remastered/processor-fan.jpg


git filter-branch --index-filter 'git rm --cached --ignore-unmatch static/*.jpg' -- --all
WARNING: git-filter-branch has a glut of gotchas generating mangled history
	 rewrites.  Hit Ctrl-C before proceeding to abort, then use an
	 alternative filtering tool such as 'git filter-repo'
	 (https://github.com/newren/git-filter-repo/) instead.  See the
	 filter-branch manual page for more details; to squelch this warning,
	 set FILTER_BRANCH_SQUELCH_WARNING=1.
Proceeding with filter-branch...

Rewrite caf8f5cad537a0546ba6509171909b8441f7299f (1/135) (0 seconds passed, remaining 0 predicted)

git-filter-repo --analyze
Processed 2072 blob sizes
Processed 135 commits
Writing reports to .git/filter-repo/analysis...done.

git filter-repo --path static/
Parsed 135 commits
New history written in 0.16 seconds; now repacking/cleaning...
Repacking your repo and cleaning out old unneeded objects
HEAD is now at 98fc3f6 weekly notes 05 (#51)
Enumerating objects: 331, done.
Counting objects: 100% (331/331), done.
Delta compression using up to 10 threads
Compressing objects: 100% (307/307), done.
Writing objects: 100% (331/331), done.
Total 331 (delta 3), reused 317 (delta 3), pack-reused 0
Completely finished after 0.87 seconds.



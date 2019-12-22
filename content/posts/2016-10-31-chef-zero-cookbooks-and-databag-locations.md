---
title: Chef Zero, Cookbooks and Data Bags locations
author: Sathya
type: post
date: 2016-10-31T13:55:00+00:00
url: /2016/10/31/chef-zero-cookbooks-and-databag-locations/
categories:
  - "Tips &amp; How-To's"
tags:
  - chef
  - chef-zero
  - data bags
  - DevOps
  - recipes

---
I like chef-zero a lot. There&#8217;s so much overlap between chef&#8217;s products: chef-zero, chef-solo, chef-apply &#8211; yes, each have their own uses, but I digress. Chef-zero has been relatively pain-free for me &#8211; except when I tried to get it running &#8211; trying to figure out why it wasn&#8217;t fetching the cookbooks was so annoying! I went and RTFM couple of times, no dice. Then I decided to not skim read and <a href="https://docs.chef.io/ctl_chef_client.html" target="_blank">read the entire thing</a>.

<!--more-->

> **chef-zero** is a very lightweight Chef server that runs in-memory on the local machine. This allows the chef-client to be run against the chef-repo as if it were running against the Chef server. chef-zero was [originally a standalone tool][1]{.reference.external}; it is enabled from within the chef-client by using the **<tt class="docutils literal"><span class="pre">--local-mode</span></tt>** option
> 
> **Local mode** does not require a configuration file, instead it will look for a **directory named** <tt class="docutils literal"><span class="pre"><strong>/cookbooks</strong></span></tt> and will set <tt class="docutils literal"><span class="pre">chef_repo_path</span></tt> to be just above that. (Local mode will honor the settings in a configuration file, if desired.) If the client.rb file is not found and no configuration file is specified, local mode will search for a knife.rb file.)

Sometimes skim reading and Ctrl+F doesn&#8217;t really go in your way. Especially if what you&#8217;re searching for and what&#8217;s referred to are nowhere close to each other. Back to topic again &#8211; for a new recipe I was working on, I needed to use databags. No problem. Wanted to do some ad-hoc checks and verification before going the <a href="https://kitchen.ci/" target="_blank">Test Kitchen</a> way. No problem. Wrote the code, then it dawned me. How and where the heck do I upload the databags to? After couple of unsuccessful converge runs, mainly because of 404 when databags were being fetched, I realized that databags were not being fetched. After some searching, I found that the databags need to be in the root directory of where you&#8217;re starting your chef-zero run. And in a directory called **data_bags**. Not databags. Sigh. Just a pro tip.

Also, bonus video: See how chef-zero came alive during a black friday line.

https://www.youtube.com/watch?v=bUYjX1SNUh8

&nbsp;

 [1]: https://github.com/chef/chef-zero
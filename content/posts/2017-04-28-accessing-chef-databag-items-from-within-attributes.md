---
title: Accessing Chef Databag Items from within attributes
author: Sathya
type: post
date: 2017-04-28T10:08:00+00:00
url: /2017/04/28/accessing-chef-databag-items-from-within-attributes/
categories:
  - "Tips &amp; How-To's"
tags:
  - chef
  - configuration management
  - data bags

---
In Chef parlance, <a href="https://docs.chef.io/data_bags.html" target="_blank" rel="noopener noreferrer">databags</a> are global variables saved in JSON format and are stored and accessible on the Chef server. Given that these are indexed and can be searched up along with the fact that they can be encrypted make them ideal candidates to store secrets such as credentials/ssh keys.

Chef provides an easy way to search and fetch databag and databag items from within a recipe:

For ex to fetch a databag called admins, it&#8217;s as easy as:

<pre>admins = data_bag('admins')</pre>

And to fetch databag items:

<pre>admins.each do |login|
    admin = data_bag_item('admins', login)
    user_name = admin['id']
    ssh_keys = admin['ssh_keys']
    groups = admin['groups']
end
</pre>

Unfortunately, the data\_bag and data\_bag_item <a href="http://stackoverflow.com/a/37445023/92837" target="_blank" rel="noopener noreferrer">helpers are not accessible from within attributes</a> and it seems as of now, the working way is to use <a href="http://www.rubydoc.info/github/opscode/chef/Chef/DataBagItem#load-class_method" target="_blank" rel="noopener noreferrer">Chef::DataBagItem.load</a> method like so:

<pre>credentials  = Chef::DataBagItem.load('admins','sathya')
</pre>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2017/04/28/accessing-chef-databag-items-from-within-attributes/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1522" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2017/04/28/accessing-chef-databag-items-from-within-attributes/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1522" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2017/04/28/accessing-chef-databag-items-from-within-attributes/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1522" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2017/04/28/accessing-chef-databag-items-from-within-attributes/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2017/04/28/accessing-chef-databag-items-from-within-attributes/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
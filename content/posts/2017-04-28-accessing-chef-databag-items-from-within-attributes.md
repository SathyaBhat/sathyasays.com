---
title: Accessing Chef Databag Items from within attributes
author: Sathyajith Bhat
type: post
date: 2017-04-28T10:08:00+00:00
url: /2017/04/28/accessing-chef-databag-items-from-within-attributes/
categories:
  - "Tips & How-To's"
tags:
  - chef
  - configuration management
  - data bags

---
In Chef parlance, <a href="https://docs.chef.io/data_bags.html" target="_blank" rel="noopener noreferrer">databags</a> are global variables saved in JSON format and are stored and accessible on the Chef server. Given that these are indexed and can be searched up along with the fact that they can be encrypted make them ideal candidates to store secrets such as credentials/ssh keys.

Chef provides an easy way to search and fetch databag and databag items from within a recipe:

For ex to fetch a databag called admins, it's as easy as:

<pre>admins = data_bag('admins')</pre>

And to fetch databag items:

<pre>admins.each do |login|
    admin = data_bag_item('admins', login)
    user_name = admin['id']
    ssh_keys = admin['ssh_keys']
    groups = admin['groups']
end
</pre>

Unfortunately, the data\_bag and data\_bag_item <a href="https://stackoverflow.com/a/37445023/92837" target="_blank" rel="noopener noreferrer">helpers are not accessible from within attributes</a> and it seems as of now, the working way is to use <a href="https://www.rubydoc.info/github/opscode/chef/Chef/DataBagItem#load-class_method" target="_blank" rel="noopener noreferrer">Chef::DataBagItem.load</a> method like so:

<pre>credentials  = Chef::DataBagItem.load('admins','sathya')
</pre>

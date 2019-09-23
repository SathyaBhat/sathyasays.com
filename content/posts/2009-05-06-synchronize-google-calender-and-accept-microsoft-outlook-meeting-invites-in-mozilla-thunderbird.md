---
title: Synchronize Google Calender and Accept Microsoft Outlook Meeting Invites in Mozilla Thunderbird
author: Sathya
type: post
date: 2009-05-06T00:17:52+00:00
url: /2009/05/06/synchronize-google-calender-and-accept-microsoft-outlook-meeting-invites-in-mozilla-thunderbird/
categories:
  - News
tags:
  - addon
  - Calender
  - cat
  - DE
  - download
  - events
  - file
  - Google
  - Home
  - IM
  - install
  - laptop
  - Lightning
  - Lightning project
  - login
  - Microsoft
  - mount
  - Mozilla
  - New
  - open source
  - os
  - PIM
  - PIM suite
  - read
  - rm
  - show
  - sync
  - tar
  - Thunderbird
  - "tips-and-howto's"
  - tutorials
  - user
  - write
  - X
  - Zindus

---
I&#8217;ve been using Mozilla Thunderbird pretty extensively past few months. Even though I do have Microsoft Outlook installed on my work laptop &#8211; with the amount of mails  that I send and receive, Outlook just dies when the Inbox size shoots up and that&#8217;s an absolute killer. One of the problems with Thunderbird is that unlike Outlook, its an email-client, and not a complete PIM suite, and my work requires me to maintain an extensive calender system. But thanks to addons, you don&#8217;t have to worry about this. Let me show you how you can convert Mozilla Thunderbird to complete PIM suite.

<!--more-->

The first thing we need to do, is have a Calender system in Mozilla Thunderbird. There are couple of addons for this, but IMO the Lightning project is probably the best of the lot. Lightning project also allows you to accept Outlook meeting invites, but we&#8217;ll get to that in a while.

Head over to Lightning project homepage, and [download the addon][1]{#aptureLink_QOLoOqb6wV} as per your platform. Next, install the addon by clicking on Tools  -> Addons -> Install and then point it to the location where you have downloaded the addon. Restart Thunderbird and you will get a Calender and tasks pane on the lower left corner, and an events sidebar.

[<img class="aligncenter size-medium wp-image-732" title="Thunderbird" src="http://sathyasays.com/wp-content/uploads/2009/05/thunderbird-300x187.png" alt="Thunderbird"   srcset="https://sathyasays.com/wp-content/uploads/2009/05/thunderbird-300x187.png 300w, https://sathyasays.com/wp-content/uploads/2009/05/thunderbird-1024x640.png 1024w, https://sathyasays.com/wp-content/uploads/2009/05/thunderbird.png 1280w" sizes="(max-width: 300px) 100vw, 300px" />][2]

Now that our calender system is ready, lets do the next step &#8211; Integration with Google calender. This requires another addon, [Provider for Google Calender][3]{#aptureLink_GXJ1JKc4aT} which basically allows  Lightning to access and write back to Google calender. Follow the same steps as mentioned above to install the addon.

Next, lets configure Thunderbird to use Google calender. Click on File -> New -> Calender -> On the nextwork radiobox. Now click on the Next button.Click on Google Calender radio box. In the location, enter the location of your Google Calender shared URL. You can obtain this URL by logging on to Google Calender and then clicking on the Settings link from the left sidebar. In the lower corner, you will see an &#8220;Calender address&#8221; section, right click on the XML button and copy the link address. Now enter this address in the Location textbox mentioned above.

[<img class="aligncenter size-medium wp-image-736" title="screenshot-create-new-calendar" src="http://sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar-300x224.png" alt="screenshot-create-new-calendar"   srcset="https://sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar-300x224.png 300w, https://sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar.png 529w" sizes="(max-width: 300px) 100vw, 300px" />][4]

Click next, you will be prompted for your Google  accounts username and password. Login you&#8217;re done! Next time you receive a meeting invite, it will be available under Invitations link!

As a bonus, if you use Google contacts to keep your contacts in Sync, use the [Zindus][5]{#aptureLink_FbGXMBaFlY} addon to Sync your Mozilla Thunderbird Addon with Google Contacts!

 [1]: http://www.mozilla.org/projects/calendar/lightning/
 [2]: http://sathyasays.com/wp-content/uploads/2009/05/thunderbird.png
 [3]: https://addons.mozilla.org/en-US/thunderbird/addon/4631
 [4]: http://sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar.png
 [5]: https://addons.mozilla.org/en-US/thunderbird/addon/6095

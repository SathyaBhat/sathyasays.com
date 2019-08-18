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

[<img data-attachment-id="732" data-permalink="https://sathyasays.com/2009/05/06/synchronize-google-calender-and-accept-microsoft-outlook-meeting-invites-in-mozilla-thunderbird/thunderbird/" data-orig-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/05/thunderbird.png?fit=1280%2C800&ssl=1" data-orig-size="1280,800" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="Thunderbird" data-image-description="<p>Thunderbird with Lightning Project addon</p>
" data-medium-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/05/thunderbird.png?fit=300%2C187&ssl=1" data-large-file="https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/05/thunderbird.png?fit=740%2C463&ssl=1" class="aligncenter size-medium wp-image-732" title="Thunderbird" src="https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/05/thunderbird-300x187.png?resize=300%2C187" alt="Thunderbird" width="300" height="187" srcset="https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/05/thunderbird.png?resize=300%2C187&ssl=1 300w, https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/05/thunderbird.png?resize=1024%2C640&ssl=1 1024w, https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/05/thunderbird.png?w=1280&ssl=1 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][2]

Now that our calender system is ready, lets do the next step &#8211; Integration with Google calender. This requires another addon, [Provider for Google Calender][3]{#aptureLink_GXJ1JKc4aT} which basically allows  Lightning to access and write back to Google calender. Follow the same steps as mentioned above to install the addon.

Next, lets configure Thunderbird to use Google calender. Click on File -> New -> Calender -> On the nextwork radiobox. Now click on the Next button.Click on Google Calender radio box. In the location, enter the location of your Google Calender shared URL. You can obtain this URL by logging on to Google Calender and then clicking on the Settings link from the left sidebar. In the lower corner, you will see an &#8220;Calender address&#8221; section, right click on the XML button and copy the link address. Now enter this address in the Location textbox mentioned above.

[<img data-attachment-id="736" data-permalink="https://sathyasays.com/2009/05/06/synchronize-google-calender-and-accept-microsoft-outlook-meeting-invites-in-mozilla-thunderbird/screenshot-create-new-calendar/" data-orig-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar.png?fit=529%2C396&ssl=1" data-orig-size="529,396" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;}" data-image-title="screenshot-create-new-calendar" data-image-description="" data-medium-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar.png?fit=300%2C224&ssl=1" data-large-file="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar.png?fit=529%2C396&ssl=1" class="aligncenter size-medium wp-image-736" title="screenshot-create-new-calendar" src="https://i0.wp.com/sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar-300x224.png?resize=300%2C224" alt="screenshot-create-new-calendar" width="300" height="224" srcset="https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar.png?resize=300%2C224&ssl=1 300w, https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar.png?w=529&ssl=1 529w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][4]

Click next, you will be prompted for your Google  accounts username and password. Login you&#8217;re done! Next time you receive a meeting invite, it will be available under Invitations link!

As a bonus, if you use Google contacts to keep your contacts in Sync, use the [Zindus][5]{#aptureLink_FbGXMBaFlY} addon to Sync your Mozilla Thunderbird Addon with Google Contacts!

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2009/05/06/synchronize-google-calender-and-accept-microsoft-outlook-meeting-invites-in-mozilla-thunderbird/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-731" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2009/05/06/synchronize-google-calender-and-accept-microsoft-outlook-meeting-invites-in-mozilla-thunderbird/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-731" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2009/05/06/synchronize-google-calender-and-accept-microsoft-outlook-meeting-invites-in-mozilla-thunderbird/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-731" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2009/05/06/synchronize-google-calender-and-accept-microsoft-outlook-meeting-invites-in-mozilla-thunderbird/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2009/05/06/synchronize-google-calender-and-accept-microsoft-outlook-meeting-invites-in-mozilla-thunderbird/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>

 [1]: http://www.mozilla.org/projects/calendar/lightning/
 [2]: https://i1.wp.com/sathyasays.com/wp-content/uploads/2009/05/thunderbird.png
 [3]: https://addons.mozilla.org/en-US/thunderbird/addon/4631
 [4]: https://i2.wp.com/sathyasays.com/wp-content/uploads/2009/05/screenshot-create-new-calendar.png
 [5]: https://addons.mozilla.org/en-US/thunderbird/addon/6095
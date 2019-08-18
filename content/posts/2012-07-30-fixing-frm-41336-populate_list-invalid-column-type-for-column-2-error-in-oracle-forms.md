---
title: 'Fixing FRM-41336: Populate_List: invalid column type for column 2 error in Oracle Forms'
author: Sathya
type: post
date: 2012-07-30T12:25:26+00:00
url: /2012/07/30/fixing-frm-41336-populate_list-invalid-column-type-for-column-2-error-in-oracle-forms/
topsy_short_url:
  - http://u.sbhat.me/MWqET8
categories:
  - Programming
tags:
  - oracle forms

---
I spent the past hour and a half trying to fix this stupid error.

Here&#8217;s the situation:

I have a Poplist(aka dropdown list/ list item).  The poplist is populated by a query defined in a Record Group. The query is on the lines of

<!--more-->

`select id, name from employees`

The column types are correctly defined. And yet I kept running into

> FRM-41336: Populate_List: invalid column type for column

error message. Looking at the description for the message:

> FRM-41336: Populate_List: invalid column type for column.
  
> Cause:The record group does not have a column of the same type.
  
> Action:Make sure record group has a column of the same type.

Translation:

All the columns in your query must of the same data type. You can&#8217;t mix a numeric & varchar column when you&#8217;re going to populate the value into a List item. Why is this stupid restriction present, I have no freaking clue. Ended up casting the id to a varchar field:

`select to_char(id), name from employees`

And all is well. For now, till another silly limitation will screw my happiness.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2012/07/30/fixing-frm-41336-populate_list-invalid-column-type-for-column-2-error-in-oracle-forms/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1120" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2012/07/30/fixing-frm-41336-populate_list-invalid-column-type-for-column-2-error-in-oracle-forms/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1120" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2012/07/30/fixing-frm-41336-populate_list-invalid-column-type-for-column-2-error-in-oracle-forms/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1120" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2012/07/30/fixing-frm-41336-populate_list-invalid-column-type-for-column-2-error-in-oracle-forms/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2012/07/30/fixing-frm-41336-populate_list-invalid-column-type-for-column-2-error-in-oracle-forms/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
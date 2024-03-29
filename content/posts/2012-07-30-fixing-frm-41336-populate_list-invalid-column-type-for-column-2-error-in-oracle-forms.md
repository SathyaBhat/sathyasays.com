---
title: 'Fixing FRM-41336: Populate_List: invalid column type for column 2 error in Oracle Forms'
author: Sathyajith Bhat
type: post
date: 2012-07-30T12:25:26+00:00
url: /2012/07/30/fixing-frm-41336-populate_list-invalid-column-type-for-column-2-error-in-oracle-forms/

categories:
  - Programming
tags:
  - oracle

---
I spent the past hour and a half trying to fix this stupid error.

Here's the situation:

I have a Poplist(aka dropdown list/ list item).  The poplist is populated by a query defined in a Record Group. The query is on the lines of



`select id, name from employees`

The column types are correctly defined. And yet I kept running into

> FRM-41336: Populate_List: invalid column type for column

error message. Looking at the description for the message:

> FRM-41336: Populate_List: invalid column type for column.
  
> Cause:The record group does not have a column of the same type.
  
> Action:Make sure record group has a column of the same type.

Translation:

All the columns in your query must of the same data type. You can't mix a numeric & varchar column when you're going to populate the value into a List item. Why is this stupid restriction present, I have no freaking clue. Ended up casting the id to a varchar field:

`select to_char(id), name from employees`

And all is well. For now, till another silly limitation will screw my happiness.

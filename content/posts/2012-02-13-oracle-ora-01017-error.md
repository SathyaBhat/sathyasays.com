---
title: Troubleshooting Oracle’s ORA-01017 errors
author: Sathya
type: post
date: 2012-02-13T11:44:31+00:00
url: /2012/02/13/oracle-ora-01017-error/
topsy_short_url:
  - https://u.sbhat.me/wwvC3q
categories:
  - Programming
tags:
  - oracle

---
Was writing this for <a href="https://stackoverflow.com" target="_blank">Stack Overflow</a>&#8216;s tag wiki on <a href="https://stackoverflow.com/tags/ora-01017/info" target="_blank">ORA-01017</a>, thought I&#8217;ll post it here as well.

ORA-01017 is the error code shown my Oracle when a login attempt to the database was not successful.

<!--more-->

The full text of the error code is:

> ORA-01017: invalid username/password; logon denied
> 
> Cause: An invalid username or password was entered in an attempt to
  
> log on to Oracle. The username and password must be the same as was
  
> specified in a GRANT CONNECT statement. If the username and password
  
> are entered together, the format is: username/password.
> 
> Action: Enter a valid username and password combination in the correct
  
> format.

<a title="ORA-0107 tips" href="https://www.dba-oracle.com/t_ora_01017.htm" target="_blank">DBA-Oracle</a> has a checklist for ORA-01017 errors. Though the core problem is incorrect credentials, the reason for incorrect credentials maybe one of the below:

  *  The user id may not be present in the target system
  * $ORACLE_SID maybe incorrectly defined, leading to a connection attempt to a wrong system
  * tnanames.ora points to an incorrect instance

Also, if you upgraded a pre-Oracle 11g instance to Oracle 11g & above, you might start encountering ORA-0107 messages. The reason is that Oracle 11g & above by default support case sensitive passwords, as opposed to previous versions where all passwords were set to upper case.

This behavior can be set to status quo by using <a title="Oracle documentation on case sensitive passwords" href="https://docs.oracle.com/cd/B28359_01/server.111/b28320/initparams211.htm#I1010299" target="_blank">SEC_CASE_SENSITIVE_LOGON</a> parameter, as explained by <a title="Oracle 11g & ORA-01017" href="https://oradim.blogspot.com/2007/11/oracle-11g-and-ora-01017-invalid.html" target="_blank">Mark Williams</a>.
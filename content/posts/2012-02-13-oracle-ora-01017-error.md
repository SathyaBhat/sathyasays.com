---
title: Troubleshooting Oracle’s ORA-01017 errors
author: Sathya
type: post
date: 2012-02-13T11:44:31+00:00
url: /2012/02/13/oracle-ora-01017-error/
topsy_short_url:
  - http://u.sbhat.me/wwvC3q
categories:
  - Programming
tags:
  - oracle

---
Was writing this for <a href="http://stackoverflow.com" target="_blank">Stack Overflow</a>&#8216;s tag wiki on <a href="http://stackoverflow.com/tags/ora-01017/info" target="_blank">ORA-01017</a>, thought I&#8217;ll post it here as well.

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

<a title="ORA-0107 tips" href="http://www.dba-oracle.com/t_ora_01017.htm" target="_blank">DBA-Oracle</a> has a checklist for ORA-01017 errors. Though the core problem is incorrect credentials, the reason for incorrect credentials maybe one of the below:

  *  The user id may not be present in the target system
  * $ORACLE_SID maybe incorrectly defined, leading to a connection attempt to a wrong system
  * tnanames.ora points to an incorrect instance

Also, if you upgraded a pre-Oracle 11g instance to Oracle 11g & above, you might start encountering ORA-0107 messages. The reason is that Oracle 11g & above by default support case sensitive passwords, as opposed to previous versions where all passwords were set to upper case.

This behavior can be set to status quo by using <a title="Oracle documentation on case sensitive passwords" href="http://docs.oracle.com/cd/B28359_01/server.111/b28320/initparams211.htm#I1010299" target="_blank">SEC_CASE_SENSITIVE_LOGON</a> parameter, as explained by <a title="Oracle 11g & ORA-01017" href="http://oradim.blogspot.com/2007/11/oracle-11g-and-ora-01017-invalid.html" target="_blank">Mark Williams</a>.

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2012/02/13/oracle-ora-01017-error/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1068" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2012/02/13/oracle-ora-01017-error/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1068" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2012/02/13/oracle-ora-01017-error/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1068" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2012/02/13/oracle-ora-01017-error/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2012/02/13/oracle-ora-01017-error/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
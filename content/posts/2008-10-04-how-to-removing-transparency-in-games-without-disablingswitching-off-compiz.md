---
title: '[How To] Removing Transparency In Games without disabling/switching off Compiz'
author: Sathya
type: post
date: 2008-10-04T07:21:23+00:00
url: /2008/10/04/how-to-removing-transparency-in-games-without-disablingswitching-off-compiz/
categories:
  - "Tips &amp; How-To's"
tags:
  - Arch
  - cat
  - ccsm
  - compiz
  - compiz fusion
  - DE
  - forums
  - fusion
  - games
  - Google
  - IM
  - internet
  - linux
  - LV
  - menu
  - move
  - moving
  - net
  - opacity
  - os
  - rm
  - switch
  - switching
  - "tips-and-howto's"
  - transparency
  - tutorials
  - Ubuntu
  - ux
  - X
  - xp

---
<div>
  <em>Admin&#8217;s Note: This solution was emailed to me by Bharath, as he was facing this problem and found a solution to this. If you want to drop a tip or a hack, just send me an email via the contact-me form and I might just publish it</em>
</div>

<div>
  Sometimes when playing native games in Linux they may appear transparent. This may feel good for some people. I felt games should be opaque so that the visibility of the game is more realistic and gameplay experience is better. I searched out Google, Compiz forums and even Ubuntu forums just to return without a proper solution. May be there is one out there in the internet and only its me who did not ponder over it. Switching off compiz-fusion may be one option. But switching off every time you run a game and switch it on after closing the game would be a frustrating job.
</div>

<div>
  <!--more-->
</div>

<div>
  Once I searched the options of compizconfig-settings-manager (ccsm) and tried the following procedure to solve the problem, and this seems to work.
</div>

### Here&#8217;s how to go about in fixing the problem:

<div>
  <ol>
    <li>
      Open ccsm (press alt+f2 type &#8220;ccsm&#8221;)
    </li>
    <li>
      Enter General Options
    </li>
    <p style="text-align: center;">
      <a href="http://img215.imageshack.us/my.php?image=generaloptionsmu5.png" target="_blank"><img class="aligncenter" src="https://i1.wp.com/img215.imageshack.us/img215/8900/generaloptionsmu5.th.png?w=740" border="0" alt="" data-recalc-dims="1" /></a>
    </p>
    
    <li>
      Go the tab named &#8220;Opacity Settings&#8221; and expand a tree named &#8220;Window opacities&#8221;.
    </li>
    <p style="text-align: center;">
      <a href="http://img113.imageshack.us/my.php?image=opacitysettingsgc1.png" target="_blank"><img src="https://i2.wp.com/img113.imageshack.us/img113/3672/opacitysettingsgc1.th.png?w=740" border="0" alt="" data-recalc-dims="1" /></a>
    </p>
    
    <li>
      There will be transparency settings for different GUI components like Menu | Window | Dialog <div>
        Double click it and locate among them an entry called DropDownMenu and remove it. You&#8217;re done.
      </div>
      
      <p style="text-align: center;">
        <a href="http://img521.imageshack.us/my.php?image=dropdownmenubk9.png" target="_blank"><img src="https://i0.wp.com/img521.imageshack.us/img521/9227/dropdownmenubk9.th.png?w=740" border="0" alt="" data-recalc-dims="1" /></a>
      </p>
      
      <div>
        DropDownMenus may appear opaque but otherwise there shouldn&#8217;t be any problems. Games will be full opaque now. Please let me know if this solution works for you or if you are having other problems.
      </div>
    </li>
  </ol>
</div>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/10/04/how-to-removing-transparency-in-games-without-disablingswitching-off-compiz/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-429" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/10/04/how-to-removing-transparency-in-games-without-disablingswitching-off-compiz/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-429" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/10/04/how-to-removing-transparency-in-games-without-disablingswitching-off-compiz/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-429" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/10/04/how-to-removing-transparency-in-games-without-disablingswitching-off-compiz/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/10/04/how-to-removing-transparency-in-games-without-disablingswitching-off-compiz/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
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
      <a href="https://img215.imageshack.us/my.php?image=generaloptionsmu5.png" target="_blank"><img class="aligncenter" src="https://img215.imageshack.us/img215/8900/generaloptionsmu5.th.png" border="0" alt="" /></a>
    </p>
    
    <li>
      Go the tab named &#8220;Opacity Settings&#8221; and expand a tree named &#8220;Window opacities&#8221;.
    </li>
    <p style="text-align: center;">
      <a href="https://img113.imageshack.us/my.php?image=opacitysettingsgc1.png" target="_blank"><img src="https://img113.imageshack.us/img113/3672/opacitysettingsgc1.th.png" border="0" alt="" /></a>
    </p>
    
    <li>
      There will be transparency settings for different GUI components like Menu | Window | Dialog <div>
        Double click it and locate among them an entry called DropDownMenu and remove it. You&#8217;re done.
      </div>
      
      <p style="text-align: center;">
        <a href="https://img521.imageshack.us/my.php?image=dropdownmenubk9.png" target="_blank"><img src="https://img521.imageshack.us/img521/9227/dropdownmenubk9.th.png" border="0" alt="" /></a>
      </p>
      
      <div>
        DropDownMenus may appear opaque but otherwise there shouldn&#8217;t be any problems. Games will be full opaque now. Please let me know if this solution works for you or if you are having other problems.
      </div>
    </li>
  </ol>
</div>

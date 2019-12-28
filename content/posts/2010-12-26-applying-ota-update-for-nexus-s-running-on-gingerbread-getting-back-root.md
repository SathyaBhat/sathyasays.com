---
title: 'Applying OTA update for Nexus S running on Gingerbread & Getting Back Root'
author: Sathya
type: post
date: 2010-12-26T02:16:57+00:00
url: /2010/12/26/applying-ota-update-for-nexus-s-running-on-gingerbread-getting-back-root/
topsy_short_url:
  - https://u.sbhat.me/enUdBy
categories:
  - Android
tags:
  - Android
  - ClockWork Recovery
  - Gingerbread
  - Nexus S
  - OTA

---
Got my hands on the [Nexus S][1] recently, and so far I&#8217;m loving it. I&#8217;m still getting to know the OS better &#8211; and with it learning more about the different ROMs, installing them and flashing them (Side note: The speed at which custom kernels & ROMs get flashed is a serious shock especially if you&#8217;re used to the slow-as-snails-on-time-machine update process that is iTunes).

Anyhow, I&#8217;ll save my thoughts on the Nexus S for a later blog post.

<!--more-->


  
Coming back, I switched to a custom Kernel + ROM + Recovery, and now when the OTA was pushed to my phone, I was apprehensive about how to apply it. A bit of research indicated that the OTA is not possible, and I&#8217;d have to flash to stock &#8211; which means all my data would be wiped.

So here&#8217;s what I did:

  * Install [Titanium Backup Pro][2] & take a backup of all my apps, data & system data.
  * Sync the backup to [DropBox][3]
  * Download [SuperUser][4] to the phone.
  * Updated ClockWork Recovery Mod (&#8220;CW&#8221;)to 3.0.0.0 by [downloading from here][5] and then flash it using
  
    `fastboot flash recovery recovery-clockwork-3.0<br />
.0.0-crespo.img`
  * Download stock 2.3.1 Nandroid [from here][6] & update it from within Clockwork Recovery.
  * Reboot phone. 2.3.1 will erase CW and replace it with stock. Install [ROM Manager][7] and allow it to install CW.
  * Install [superuser][4] by rebooting the phone into CW & choosing to install Zip from the phone.

So, at this stage, you will have a clean, stock phone with root privileges available. Complete the process by

  * Installing [BusyBox][8] and TitaniumBackup
  * Restore all your apps & data by using TitaniumBackup
Also: note that 2.3.1 features a change which will replace CW with stock recovery on every reboot. To avoid this, use Root Explorer, find /etc/install-recovery and rename it to /etc/install-recovery.never ( or whatever) to prevent CW to be overwritten by stock recovery. 

Compiled from my experiments after getting confused over various threads in [XDA][9].

 [1]: https://post.sathyabh.at/hello-to-the-nexus
 [2]: https://www.cyrket.com/p/android/com.keramidas.TitaniumBackup/
 [3]: https://db.tt/Bfe1DYU
 [4]: https://forum.xda-developers.com/showthread.php?t=682828
 [5]: https://koush.kanged.net/cm/recoveries/
 [6]: https://www.mediafire.com/?ontvvh8z9h9lb7a
 [7]: https://www.appbrain.com/app/rom-manager/com.koushikdutta.rommanager
 [8]: https://www.appbrain.com/app/busybox/stericson.busybox
 [9]: https://forum.xda-developers.com/

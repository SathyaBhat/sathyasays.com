---
title: openSUSE 10.3 On PlayStation 3
author: Sathya
type: post
date: 2007-10-08T14:02:22+00:00
url: /2007/10/08/playstation-3-on-opensuse-103/
categories:
  - News
tags:
  - beta
  - bin
  - bluetooth
  - boot
  - DE
  - Desktop
  - distro
  - distros
  - dl
  - download
  - driver
  - drivers
  - DVD
  - exe
  - Fedora
  - file
  - find
  - flash
  - IM
  - install
  - iso
  - KDE
  - keyboard
  - linux
  - media
  - menu
  - mount
  - net
  - openSuSE
  - os
  - partition
  - Partitions
  - record
  - repo
  - repos
  - repositories
  - repository
  - Resolution
  - rm
  - root
  - Screen
  - software
  - support
  - SUSE
  - switch
  - sync
  - tar
  - Ubuntu
  - update
  - updating
  - usb
  - user
  - ux
  - warning
  - X
  - xp
  - YaST

---
<font size="2">The Sony PLAYSTATION 3 (PS3) is based on a 3.2GHz <a href="http://www.wikipedia.org/wiki/Cell_Microprocessor" class="extiw" title="wikipedia:Cell Microprocessor">Cell Microprocessor</a>, with 256MByte GDDR-VRAM. The processor is <a href="http://en.opensuse.org/POWER%40SUSE" title="POWER@SUSE">PowerPC</a> compatible. The alliance of (IBM/Sony/Toshiba) who created the Cell processor have been active creating Linux kernel patches for the processor since Linux Kernel 2.6.13. Sony has created kernel patches specific for the PS3 in Linux Kernel 2.6.22, as well as maintaining the GNU toolchain (gcc, binutils etc).</font>

## <font size="2">Hardware Requirements</font>

<font size="2"></p> 

<li>
  A computer to download and copy files on to media.
</li>
<li>
  Playstation3 with: <ul>
    <li>
      USB Keyboard and Mouse
    </li>
  </ul>
</li>

<li>
  Any of the following recording media: <ul>
    <li>
      USB Flash or HD drive
    </li>
    <li>
      CD-R, CD-RW, DVD-R, DVE+R, DVD-RW, DVD+RW, BD-R, or BD-RE disc
    </li>
    <li>
      If the PS3 has memory card slots: Memory Stick, SD memory card, or CompactFlash.
    </li>
  </ul>
</li>

<p>
  </font></ul> 
  
  <p>
    <font size="2"><a title="Software_Requirements" name="Software_Requirements"></a></font>
  </p>
  
  <h2>
    <font size="2">Software Requirements</font>
  </h2>
  
  <ul>
    <font size="2"></p> 
    
    <li>
      <a href="http://download.opensuse.org/" class="external text" title="http://download.opensuse.org/" rel="nofollow">openSUSE 10.3 for PPC</a>
    </li>
    <li>
      <a href="http://download.opensuse.org/distribution/SL-OSS-factory/inst-source/PS3/otheros/otheros.bld" class="external text" title="http://download.opensuse.org/distribution/SL-OSS-factory/inst-source/PS3/otheros/otheros.bld" rel="nofollow">Other OS Boot loader</a> available on installation media aswell
    </li>
    <p>
      </font></ul> 
      
      <p>
        <font size="2"><a title="Instructions" name="Instructions"></a></font>
      </p>
      
      <h2>
        <font size="2"> Instructions</font>
      </h2>
      
      <p class="editsection" style="float: right; margin-left: 5px">
        <font size="2"> </font>
      </p>
      
      <p>
        <font size="2"><a title="Preparing_Media" name="Preparing_Media"></a></font><!--more-->
      </p>
      
      <h3>
        <font size="2"> Preparing Media</font>
      </h3>
      
      <p>
        <font size="2">Just download the PPC edition of OpenSuse 10.3 and burn it to a DVD media using your favorite burning tool.</font>
      </p>
      
      <p>
        <font size="2"><strong> NOTE: PS3 bootloader can now be updated from OpenSuse 10.3 installation media</strong></font>
      </p>
      
      <p>
        <font size="2"><strong>Technical Note</strong></font>
      </p>
      
      <ul>
        <font size="2"></p> 
        
        <li>
          On your recording media there is the following folder structure, It is a requirement to use single-byte characters only.
        </li>
        <p>
          </font></ul> 
          
          <pre><font size="2">PS3</font><font size="2">
</font><font size="2">|-otheros</font></pre>
          
          <p>
            <font size="2">It is possible to download the Boot loader here <a href="http://download.opensuse.org/distribution/SL-OSS-factory/inst-source/PS3/otheros/otheros.bld" class="external text" title="http://download.opensuse.org/distribution/SL-OSS-factory/inst-source/PS3/otheros/otheros.bld" rel="nofollow">otheros.bld</a></font>
          </p>
          
          <p>
            <font size="2"><a title="Installation" name="Installation"></a></font>
          </p>
          
          <h3>
            <font size="2"> Installation</font>
          </h3>
          
          <p>
            <font size="2"><a title="Preparing_the_PS3" name="Preparing_the_PS3"></a></font>
          </p>
          
          <h4>
            <font size="2">Preparing the PS3</font>
          </h4>
          
          <p>
            <font size="2"><strong>NOTE:</strong> Updating your PS3 to the latest firmware is recommended before proceeding</font>
          </p>
          
          <ul>
            <font size="2"></p> 
            
            <li>
              Select <strong>Settings</strong> -> <strong>System Settings</strong> -> <strong>Format Drive</strong>. Create two partitions one for the PS3s normal use and one for openSUSE. Note that you will lose any saved game info.
            </li>
            <li>
              Insert the media in the PS3
            </li>
            <li>
              Select <strong>Settings</strong> -> <strong>System Settings</strong> -> <strong>Install Other OS</strong>. The PS3 will display the installers it can find. Click <strong>OK</strong> to start the installer.
            </li>
            <li>
              Follow the instructions of the Sony installer.
            </li>
            <li>
              To boot into the Other OS, select <strong>Settings</strong> > <strong>System Settings</strong> > <strong>Default System</strong> > <strong>Other OS</strong>. This causes the &#8216;Other OS Boot loader&#8217; to be loaded on every boot.
            </li>
            <p>
              </font></ul> 
              
              <p>
                <em><font size="2">To force the PS3 to boot up normally hold down the Power button for about 5 seconds or more at power on. This is in case you do not have a keyboard. with a keyboard you can use ps3-boot-game-os command to reboot to the PS3 game os.</font></em>
              </p>
              
              <p>
                <font size="2">Installing openSUSENOTE: it is not recommended to enable Online Repositories during installation as the PS3 might run out of memory. Please add Online Repositories *after* the installation using YaST.</font>
              </p>
              
              <p>
                <font size="2"><strong>Installation for OpenSuse 10.3 Final</strong></font>
              </p>
              
              <ul>
                <font size="2"></p> 
                
                <li>
                  Insert openSUSE 10.3 installation media in the PS3
                </li>
                <li>
                  Boot Other OS, select <strong>Settings</strong> > <strong>System Settings</strong> > <strong>Default System</strong> > <strong>Other OS</strong>.
                </li>
                <li>
                  Select the &#8220;install&#8221; boot option from boot screen and press enter
                </li>
                <li>
                  Graphical installer will start, just follow onscreen instructions
                </li>
                <p>
                  </font></ul> 
                  
                  <p>
                    <font size="2"><strong>Installation for OpenSuse >= 10.3 Beta 3</strong></font>
                  </p>
                  
                  <ul>
                    <font size="2"></p> 
                    
                    <li>
                      Insert openSUSE 10.3 installation media in the PS3
                    </li>
                    <li>
                      Boot Other OS, select <strong>Settings</strong> > <strong>System Settings</strong> > <strong>Default System</strong> > <strong>Other OS</strong>.
                    </li>
                    <li>
                      Select the &#8220;install&#8221; boot option from boot screen and press enter
                    </li>
                    <li>
                      You will get a <strong>warning</strong> saying that the repository is broken, the system propose 1) OK or 2) Back, just ignore and enter 1
                    </li>
                    <li>
                      Graphical installer start then, just follow onscreen instructions
                    </li>
                    <p>
                      </font></ul> 
                      
                      <p>
                        <font size="2"><strong>Installation for OpenSuse 10.3 Beta 2</strong></font>
                      </p>
                      
                      <p>
                        <font size="2"><strong>MD5 checksum of PPC edition is missing on download page</strong> Here is mine, burn successfuly, and after an installer media check</font>
                      </p>
                      
                      <p>
                        <font size="2">$ md5sum.exe openSUSE-10.3-Beta2-DVD-ppc.iso</font>
                      </p>
                      
                      <p>
                        <font size="2">69f49fca918ad7c72de027617b4cc97d openSUSE-10.3-Beta2-DVD-ppc.iso</font>
                      </p>
                      
                      <ul>
                        <font size="2"></p> 
                        
                        <li>
                          Insert openSUSE 10.3 installation media in the PS3
                        </li>
                        <li>
                          Boot Other OS, select <strong>Settings</strong> > <strong>System Settings</strong> > <strong>Default System</strong> > <strong>Other OS</strong>.
                        </li>
                        <li>
                          Select the &#8220;install&#8221; boot option from boot screen and press enter
                        </li>
                        <li>
                          You will get a <strong>warning</strong> saying that the repository is broken, the system propose 1) OK or 2) Back, just ignore and enter 1
                        </li>
                        <li>
                          Graphical installer start then, just follow onscreen instructions
                        </li>
                        <li>
                          A media check will occur, it is recommended to run it
                        </li>
                        <li>
                          Do not skip the network install, the repository cache (remember warning at beginning) will be rebuild
                        </li>
                        <li>
                          Estimated Time for install <ul>
                            <li>
                              KDE default package 58 min but real 35 min
                            </li>
                          </ul>
                        </li>
                        
                        <li>
                          After reboot, the system hang while trying to unmount a device, just reboot PS3 by pressing power off/power on button, install will continue
                        </li>
                        <li>
                          You can create root password, user logging etc&#8230;
                        </li>
                        <li>
                          bluetooth is detected, video unrecognized (but working) and sound unsupported
                        </li>
                        <li>
                          the screen went black in runlevel 5 for at least 4 minute before displaying finally the desktop
                        </li>
                        <li>
                          Load displayed by command top is quite high (> 2.50), sad that PS3 main memory (256Mb) not bigger is&#8230;
                        </li>
                        <p>
                          </font></ul> 
                          
                          <p>
                            <font size="2"><strong>Installation for OpenSuse < 10.3 Beta 1</strong></font>
                          </p>
                          
                          <p>
                            <font size="2">NOTE: openSUSE 10.3 Alpha7 is the first release to have initial support for Playstation 3</font>
                          </p>
                          
                          <p>
                            <font size="2">Following are some basic steps to have a first glimpse at what you can expect from openSUSE on PS3. Please keep in mind that this is in an early stage.</font>
                          </p>
                          
                          <ul>
                            <font size="2"></p> 
                            
                            <li>
                              Insert openSUSE 10.3 installation media in the PS3
                            </li>
                            <li>
                              boot Other OS, select <strong>Settings</strong> > <strong>System Settings</strong> > <strong>Default System</strong> > <strong>Other OS</strong>.
                            </li>
                            <li>
                              select the &#8220;install&#8221; boot option from boot screen and press enter
                            </li>
                            <li>
                              select <strong>3) Kernel Modules (Hardware Drivers)</strong>
                            </li>
                            <li>
                              select <strong>1) Load ppc Modules</strong>
                            </li>
                            <li>
                              select <strong>17) ps3rom : PS3 CDROM</strong>
                            </li>
                            <li>
                              go back to Main Menu by just pressing enter
                            </li>
                            <li>
                              select <strong>4) Start Installation or System</strong>
                            </li>
                            <li>
                              select <strong>1) Start Installation or Update</strong>
                            </li>
                            <li>
                              select <strong>1) CD-ROM</strong>
                            </li>
                            <p>
                              </font></ul> 
                              
                              <p>
                                <font size="2">Now you can perform a normal installation with YaST. This may take some time so please be patient, the PS3 only has a very limited amount of RAM.</font>
                              </p>
                              
                              <p class="editsection" style="float: right; margin-left: 5px">
                                <font size="2"> </font>
                              </p>
                              
                              <p>
                                <font size="2"><a title="Known_Problems" name="Known_Problems"></a></font>
                              </p>
                              
                              <h2>
                                <font size="2"> Known Problems</font>
                              </h2>
                              
                              <p>
                                <font size="2"><strong> General issues </strong></font>
                              </p>
                              
                              <ul>
                                <font size="2"></p> 
                                
                                <li>
                                  The kernel tries to autodetect the best resolution for your screen. In case you end up with a black screen and your monitor is out of sync try pressing &#8216;c&#8217; and afterwards &#8216;1&#8217;. This will switch the resolution to 720p. However, this will not affect the kernel you are going to boot via kexec. In case you want to manually specify a resolution append the following to the kernel commandline &#8220;video=ps3fb:mode:<X>&#8221;, where <X> specifies the video mode you want to use. [0 <= X <= 42]
                                </li>
                                <p>
                                  </font></ul> 
                                  
                                  <p>
                                    <font size="2"><strong>Issues with openSUSE 10.3 Beta 1</strong></font>
                                  </p>
                                  
                                  <ul>
                                    <font size="2"></p> 
                                    
                                    <li>
                                      CDROM driver is broken, after loading it (select 3) Kernel Modules (Hardware Drivers) select 1) Load ppc Modules select 17) ps3rom : PS3 CDROM) I can choose CD-ROM as source, but it is not working and I am blocked in that menu
                                    </li>
                                    <p>
                                      </font></ul> 
                                      
                                      <p>
                                        <font size="2"><strong>Issues with openSUSE 10.3 Alpha7</strong></font>
                                      </p>
                                      
                                      <ul>
                                        <font size="2"></p> 
                                        
                                        <li>
                                          Restart during installation fails. Manual reboot is required
                                        </li>
                                        <li>
                                          After the installation is finished the network interface may not be brought up properly
                                        </li>
                                        <li>
                                          boot-game-os is broken, returning to Sony OS is only possible by holding down the power button for about 5 seconds or more at power on
                                        </li>
                                        <p>
                                          </font></ul> 
                                          
                                          <p class="editsection" style="float: right; margin-left: 5px">
                                            &nbsp;
                                          </p>
                                          
                                          <p>
                                            <font size="2"><a title="Resources" name="Resources"></a></font>
                                          </p>
                                          
                                          <h2>
                                            <font size="2"> Resources</font>
                                          </h2>
                                          
                                          <ul>
                                            <font size="2"></p> 
                                            
                                            <li>
                                              <a href="http://www.kernel.org/pub/linux/kernel/people/geoff/cell" class="external text" title="http://www.kernel.org/pub/linux/kernel/people/geoff/cell" rel="nofollow">PS3 Linux Distributor&#8217;s Starter Kit</a>
                                            </li>
                                            <p>
                                              </font></ul> 
                                              
                                              <p class="editsection" style="float: right; margin-left: 5px">
                                                &nbsp;
                                              </p>
                                              
                                              <p>
                                                <font size="2"><a title="Other_Distros_on_PS3" name="Other_Distros_on_PS3"></a></font>
                                              </p>
                                              
                                              <h2>
                                                <font size="2"> Other Distros on PS3</font>
                                              </h2>
                                              
                                              <ul>
                                                <font size="2"></p> 
                                                
                                                <li>
                                                  <a href="http://ps3.qj.net/PS3-Linux-The-void-has-been-filled-Full-install-instructions-for-Fedora-Core-5-/pg/49/aid/73144" class="external text" title="http://ps3.qj.net/PS3-Linux-The-void-has-been-filled-Full-install-instructions-for-Fedora-Core-5-/pg/49/aid/73144" rel="nofollow">Fedora 5 on PS3</a>
                                                </li>
                                                <li>
                                                  <a href="http://ubuntuforums.org/showthread.php?t=316047" class="external text" title="http://ubuntuforums.org/showthread.php?t=316047" rel="nofollow">Ubuntu on PS3</a> &#8211; Installs Ubuntu by using basic Fedora installation
                                                </li>
                                                <p>
                                                  </font></ul> 
                                                  
                                                  <p>
                                                    Source: <a href="http://en.opensuse.org/PS3">openSuSE</a>
                                                  </p>
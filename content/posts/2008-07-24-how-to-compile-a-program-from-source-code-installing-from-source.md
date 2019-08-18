---
title: '[How To] Compile and Install a Program From Sources'
author: Sathya
type: post
date: 2008-07-24T18:29:01+00:00
url: /2008/07/24/how-to-compile-a-program-from-source-code-installing-from-source/
categories:
  - "Tips &amp; How-To's"
tags:
  - Arch
  - bin
  - bluez
  - cat
  - commands
  - compiling
  - DE
  - dl
  - download
  - exe
  - exits
  - file
  - find
  - install
  - iso
  - linux
  - move
  - notes
  - open source
  - os
  - package manager
  - read
  - repo
  - repos
  - repositories
  - RIA
  - rm
  - root
  - Screen
  - script
  - scripts
  - software
  - tar
  - tips
  - "tips-and-howto's"
  - tutorials
  - ux
  - X

---
In this day modern day, most software installations can be done using repositories and package managers. However, you _might_ face a situation of having only the source files availalble with you – you probably would want to try out bleeding edge software, which hasn’t been packaged yet, or isn’t available in the repos yet.

So if you _really_ want to try it out, then the only way would be to download the source files and compile them.

Contrary to what most people think – Compiling from sources isn’t that complicated – the entire process takes 3 commands. 

<!--more-->

  * ./configure 
  * make 
  * make install 

Let’s have a look at each of these steps now.

### Prerequisites 

Before you start compiling, you need to extact the source files, as most of them come as either tar(.tar), gzipped tar(.tar.gz , .tgz) or as bzipped tar file(.tar.bz2). Any decent archiver should extract it.&#160; You can do it via the command line by typing

`tar xvfz package-name.tar.gz` (for gzipped files) or

`tar xvfj package-name.tar.bz2` (for bzipped files)

You should also have the required header files(kernel header files, tools such as gcc, make, bison etc). Don’t worry, if you’re missing any one file the configure step will tell you something is missing.

### Compiling

Let’s now get to the compiling stage.First cd to the directory where you extracted the files by typing

`cd /path/to/directory/of/source`

Then type 

./configure

Yes, the “.” is there. This step just checks your system and assigns values for system-dependent variables. These values are used for generating a Makefile. The Makefile in turn is used for generating the actual binary.

<div>
  When you run the configure script, you&#8217;ll see a bunch of weird messages scrolling on your screen. This is normal and you shouldn&#8217;t worry about it. If configure finds an error, it complains about it and exits.
</div>

For example, here’s a snippet of the messages that might be flowing

> checking dynamic linker characteristics&#8230; GNU/Linux ld.so   
> checking whether to build static libraries&#8230; no   
> configure: creating libtool   
> checking for ppoll&#8230; yes   
> checking for pkg-config&#8230; /usr/bin/pkg-config   
> checking pkg-config is at least version 0.9.0&#8230; yes   
> checking for BLUEZ&#8230; yes   
> checking for GLIB&#8230; yes   
> checking for GMODULE&#8230; yes   
> checking for dlopen in -ldl&#8230; yes

If some file or library is missing, you’ll get a message like 

> checking for DBUS&#8230; no   
> configure: error: D-Bus library is required

If all is fine,the configure program will exit gracefully, like this

> config.status: creating test/Makefile   
> config.status: creating scripts/Makefile   
> config.status: creating config.h   
> config.status: executing depfiles commands   
> sathya@sathya:~/bluez-utils-3.36> 

Next, we issue the make command, 

`sathya@sathya:~/bluez-utils-3.36> make`

This will do the actual build and compile of the sources. Again you’ll see a bunch of weird messages flowing by the screen(geek porn! :P ) and once done, you’ll fall back to the prompt. Again if some error has occurred you will be notified

### Installation

The final step, is to install the binaries and the libraries that were built in the above step. This requires root privileges. So for that su to root and and issue the make install command

`sathya@sathya:~/bluez-utils-3.36>su root`

`root@sathya:~/bluez-utils-3.36>make install` 

That’s it! You’ve successfully compiled the program from its source and installed it. Easy isn’t it?

Some notes: 

  1. The package will contain a README or an INSTALL file. It’s recommended that you read it before you start compiling, so that you might be spared of some nasty surprises 
  2. Uninstalling programs installed by the above step is tricky, you can’t use package managers to remove them. For that you’ll have to cd to directory where you installed it from and issue make uninstall. For this reason I recommend, that you keep a separate directory for storing all these “compile-from-source” type of files 

<div class="wlWriterSmartContent" id="scid:0767317B-992E-4b12-91E0-4F059A8CECA8:cc24eaf5-ca0d-436d-95b2-25b799855bcb" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px">
  Technorati Tags: <a href="http://technorati.com/tags/linux" rel="tag">linux</a>,<a href="http://technorati.com/tags/opensource" rel="tag">opensource</a>,<a href="http://technorati.com/tags/commands" rel="tag">commands</a>,<a href="http://technorati.com/tags/tutorials" rel="tag">tutorials</a>,<a href="http://technorati.com/tags/tips+and+how-to's" rel="tag">tips and how-to&#8217;s</a>,<a href="http://technorati.com/tags/compiling" rel="tag">compiling</a>,<a href="http://technorati.com/tags/source" rel="tag">source</a>,<a href="http://technorati.com/tags/sathya" rel="tag">sathya</a>,<a href="http://technorati.com/tags/sathyasays.com" rel="tag">sathyasays.com</a>,<a href="http://technorati.com/tags/sathyasays" rel="tag">sathyasays</a>
</div>

<div class="sharedaddy sd-sharing-enabled">
  <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
    <h3 class="sd-title">
      Share this:
    </h3>
    
    <div class="sd-content">
      <ul>
        <li class="share-pocket">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2008/07/24/how-to-compile-a-program-from-source-code-installing-from-source/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
        </li>
        <li class="share-twitter">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-331" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2008/07/24/how-to-compile-a-program-from-source-code-installing-from-source/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
        </li>
        <li class="share-facebook">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-331" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2008/07/24/how-to-compile-a-program-from-source-code-installing-from-source/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
        </li>
        <li class="share-linkedin">
          <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-331" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2008/07/24/how-to-compile-a-program-from-source-code-installing-from-source/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
        </li>
        <li class="share-email">
          <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2008/07/24/how-to-compile-a-program-from-source-code-installing-from-source/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
        </li>
        <li class="share-end">
        </li>
      </ul>
    </div>
  </div>
</div>
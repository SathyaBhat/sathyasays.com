---
title: '[How To]Setup a BSNL DataOne BroadBand connection or a DSL Connection in Linux'
author: Sathya
type: post
date: 2008-10-09T18:47:19+00:00
url: /2008/10/10/how-tosetup-a-bsnl-dataone-broadband-connection-or-a-dsl-connection-in-linux/
categories:
  - "Tips & How-To's"
tags:
  - commands
  - linux
  - tutorials


---

Remember that all these assumes that your router is connected to the LAN port, if it's connected to the USB port, then disconnect it and connect to the LAN port. If you dont have a LAN card, then consider getting one. It's cheap, costs around Rs. 200. 

Next, it's best to have the router configured in pppoe mode. In this case you just have to switch on the router, the router and DHCP will take care of the rest. 

If you're unsure whether your router is in PPPoE more or bridge mode, If you have used a dialer in Windows, then your router is in bridge mode. In this case, open the terminal and type 

> `sudo pppoeconf`

Next, answer yes to all questions and enter the username and password when prompted. 
  
Please note that this is a one type setup. 

To connect, open the terminal and type 

> `pon dsl-provider`

To terminate the connection type 

> `poff`

Please note that I still recommend configuring your router to PPPoE mode for hassle-free net connection under Linux. if anyone else has or uses a different method, then do please mention them in the comments.

If you don't want to use the terminal for connecting/disconnecting then, follow the below steps:.
  
Note that the one-time setup has to be done as mentioned above. Once this is done, to create an icon for launching the connection, 
  
Right click on the desktop and Click on Create Launcher. In the Type dropdown list, choose Application in Terminal. Give a name like, Connect to DataOne. In the command type 

> `pon dsl-provider`

`Click OK. That's it! Double click on the icon to Connect!`

**For Fedora, follow the below mentioned steps**

Launch the terminal. Type 

> `adsl-setup`

It will ask for

> Enter your Login Name

Type

> `<username>@dataone`

for eg: if username is SathyaSays then enter 
  
SathyaSays@dataone for username 
  
Next it will ask for

> Interface

Type

> `/dev/eth0`

<- note it is eth0(ie, the number 0, not the letter o) 

Next when prompted for 

> Enter the demand value

just press enter 

Next it will ask 

> Please enter the IP address of your ISP's primary DNS server

Just type `server`
  
Next it will ask for

> PASSWORD

Enter the password of your Dataone/DSL account

Next, it will ask for

> USERCTRL

type yes or just press enter 
  
Next it will ask for

> FIREWALLING

type `1`
  
Finally it will ask for 

> Do you want to start this connection at boot time?

Type

> `no`

This is the one type setup. 
  
To start the connection type 
  
`adsl-start`

To terminate the connection type 
  
`adsl-stop`
  
To know the status of the connection type 
  
`adsl-status`

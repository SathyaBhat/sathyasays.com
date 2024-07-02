---
title: How to get fzf working in PowerShell
author: Sathyajith Bhat
type: post
date: 2023-04-11
url: /2023/04/11/powershell-fzf-psfzf
summary: Here's how you can get the goodness of fuzzy search in your PowerShell terminal with fzf.
featureimage: https://i.sathyabh.at/ss/fzf-docker-example.png
meta_image: https://i.sathyabh.at/ss/fzf-docker-example.png
categories:
  - DevOps
  - "Tips & How-To's"
tags:
  - fzf
  - powershell
  - opensource

---
### What's fzf?

Have you ever been in a situation where you're trying to recall some program or command that you entered in your terminal a while back and can't recall the exact command? Wouldn't it be nice if you could do a search in your terminal history loosely based on what you'd typed previously? Enter [fzf](https://github.com/junegunn/fzf), for that's what it does. fzf is a command-line [fuzzy finder](https://en.wikipedia.org/wiki/Approximate_string_matching) (hence 'fzf') that can look at your shell command history, processes, bookmarks and more. 

fzf is a seriously awesome tool and every single of my *nix boxes have it installed. However, I use Windows a fair bit and wanted to see if there's a way to get fzf running for PowerShell. Thanks to [Michael Kelley and PSFzf](https://github.com/kelleyma49/PSFzf) this is possible!

### PSFzf

PSFzf is a PowerShell module that wraps fzf. This means you can use all the goodness of fzf in a PowerShell session. 

### Installing 

You can install PSFzf and fzf via a package manager like [Chocolatey](https://chocolatey.org/) or [Scoop](https://scoop.sh/). I used Scoop to install fzf. Before you proceed, install Scoop using the below command in a PowerShell session as mentioned in [Scoop's website](https://scoop.sh/). 

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser # Optional: Needed to run a remote script the first time
irm get.scoop.sh | iex # irm == invoke web request, ie download this file. iex == invoke expression, ie, evaluate the command.
```

Install fzf using the below command.

```powershell
scoop install fzf
```

Now install PSFzf using the below command

```powershell
Install-Module -Name PSFzf
```

### Using 

Now that they are installed, you'll need to update your PowerShell profile file so that the keybindings are installed and PSFzf is ready to use.

From your PowerShell terminal, open an editor with the location of your PowerShell profile file. This is easily done by the below command in a PowerShell session

```powershell
notepad $PROFILE
```

Notepad should open a file called `Microsoft.PowerShell_profile.ps1`. Don't be surprised if it's empty. Paste the below command 

```powershell
Set-PsFzfOption -PSReadlineChordProvider 'Ctrl+t' -PSReadlineChordReverseHistory 'Ctrl+r'
```

This will map `Ctrl`+`t` to invoke PSReadline. This also maps `Ctrl`+`r` to show the last few commands you used. Save it, close your editor and open a new PowerShell session. 

So, if you want to search for a previous command, press `Ctrl`+`r` and you'll get a prompt and fzf will show the last few commands you had used. Here, you can type what you want to search for, and fzf will search and show the matching commands. In the example below see how fzf shows the commands related to `docker run` passing an environment variable, even though my command is only searching for fraction of it.

!["Example of docker run command passing an environment variable"](https://i.sathyabh.at/ss/fzf-docker-example.png)

You can save a lot of time by this approach I'm sure. Hope this helps. Note: If PowerShell is not your thing, you can install this on Linux/Mac as well. 

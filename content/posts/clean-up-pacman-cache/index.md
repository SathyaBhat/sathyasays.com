+++
title = "Clean up pacman cache automatically on Arch Linux"
author = "Sathyajith Bhat"
type = "post"
date = 2025-12-31
url = "/clean-up-pacman-cache-automatically-on-arch-linux/"
summary = "Automatically clean up pacman cache on Arch Linux"
categories = ["Linux", "Arch Linux", "Pacman"]
tags = ["linux", "arch", "pacman", "pacman-cache", "paccache"]
featureimage = https://i.sathyabh.at/ss/archlinux-logo.png
+++

I use Arch, btw. The [pacman](https://pacman.archlinux.page/) [package manager](https://en.wikipedia.org/wiki/Package_manager "wikipedia:Package manager") is one of the major unique features of [Arch Linux](https://wiki.archlinux.org/title/Arch_Linux "Arch Linux"). pacman keeps the system up-to-date by synchronizing package lists with the master server. This model also allows the user to download/install packages with a simple command, complete with all required dependencies.

Pacman also stores its downloaded packages in `/var/cache/pacman/pkg/` and does not remove old versions automatically. This lets for packages to be downgraded/rolled back without having to download the previous version.

However, since the old packages are not cleaned up, this cache can grow indefinitely, and to a large extent. 
Pacman comes with some additional flags that can help prune this cache - most notably, you’ll see references commands like below

```bash
pacman -Rns $(pacman -Qdtq)
```

or 

```bash
pacman -Scc
```

Having to do this repeatedly can be an annpoying thing and I wanted an automated way. Doing a bit of search, I came across [`paccache-hook`](https://aur.archlinux.org/packages/paccache-hook) - a simple utility that hooks into pacman’s post-transaction hooks to clean up the cache automatically.

paccache installs a [hook](https://wiki.archlinux.org/title/Pacman#Hooks) to cleanup the pacman package cache using [paccache](https://man.archlinux.org/man/paccache.8) whenever you run pacman. This ensures the pacman cache is cleaned up whenever you use pacman regularly.

Here's an example output of the hook running automatically and cleaning up the cache:

```bash
:: Running post-transaction hooks...
(1/2) Arming ConditionNeedsUpdate...
(2/2) Removing old packages from pacman cache...
Removing old installed packages...

==> finished: 136 packages removed (disk space saved: 2.57 GiB)
Removing old uninstalled packages...

==> finished: 23 packages removed (disk space saved: 4.24 MiB)
```

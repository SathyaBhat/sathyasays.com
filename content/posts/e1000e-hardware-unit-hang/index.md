+++
title = "My Home Server Went Offline for 8 Hours: Debugging an Intel e1000e Hardware Unit Hang"
author = "Sathyajith Bhat"
type = "post"
date = 2026-11-12
url = "/e1000e-hardware-unit-hang/"
summary = "My home server dropped off the network for eight hours. Here's how I tracked it down and the fix."
categories = ["Linux"]
tags = ["linux", "arch", "networking", "e1000e", "networkmanager", "self-hosting"]
+++

Around 2:20 in the afternoon, my home server, wraeclast, stopped responding. SSH timed out, the services behind Cloudflare Tunnel were down, and my [Cronitor](https://cronitor.io/) heartbeat started alerting (on a side note - Cronitor, or other similar services such as [Dead Man's Snitch](https://deadmanssnitch.com/), are excellent if you want to know when your server goes silent without wanting to set up an elaborate Rube Goldberg machine of monitoring and alerting).

The home server is really a Lenovo ThinkStation P340 workstation hooked to my LAN - there's no keyboard, mouse or KVM connected to it. Since all network connectivity was failing, I had no other option but to reboot it. Once it was back up, I went digging through the logs to find out what happened.

### Diving in

Once my containers were up, the first thing I looked at was the metrics in [Beszel](https://www.beszel.dev/). Surprisingly, all metrics seemed ok, with the exception of elevated CPU load. My original assumption was that the OS itself had locked up, but the journal proved otherwise. It ran right up to the reboot, and there were no out-of-memory kills, hung tasks, soft lockups, disk errors or thermal events.

The kernel log had something else, though. Starting at 03:19:07 UTC (2:19 PM local), this message showed up every two seconds:

```
e1000e 0000:00:1f.6 eno2: Detected Hardware Unit Hang:
  TDH                  <7f>
  TDT                  <c7>
  next_to_use          <c7>
  next_to_clean        <7e>
buffer_info[next_to_clean]:
  time_stamp           <17f4d7dd5>
  next_to_watch        <7f>
  jiffies              <180aa1740>
  ...
```

By the time I rebooted at 10:19 PM, the kernel had logged it over **14,000 times**. So evidently, while everything was running, the NIC locked up and stopped responding - which explains why the heartbeat to Cronitor and everything else started failing.

At this point, I had reached the limit of what diagnosis I could do by myself, so I launched Pi, switched to Opus 5.5 (connected via [Pi Provider Kiro](https://github.com/mikeyobrien/pi-provider-kiro)) to start looking. What follows is Pi/Opus's investigation.

### What the hang message means

The NIC is the onboard Intel I219-LM, the gigabit controller built into Intel's 400 series chipsets. It uses the `e1000e` driver.

The driver sends packets by putting them in a ring buffer and telling the NIC how far it has filled the ring. The NIC works through the ring and reports its own position back:

- **TDT** (transmit descriptor tail) is where the driver has filled up to: `0xc7`.
- **TDH** (transmit descriptor head) is where the NIC has got to: `0x7f`.

The NIC had stopped at slot `0x7f` and never moved past it. The `time_stamp` of the stuck packet was the same in every one of the 14k+ messages. The difference between that and [`jiffies`](https://blogs.oracle.com/linux/jiffies-the-heartbeat-of-the-linux-operating-system) showed the packet had been stuck for over six hours by the time I looked at one of the later messages.

The driver normally recovers from this with a `Reset adapter unexpectedly` message. That never happened here. The interface stayed `UP` and the link stayed connected, but nothing was being sent. Only the reboot cleared it.

### TSO and the I219

This is a long-standing problem with these Intel NICs. The common workaround is to turn off **TCP segmentation offload (TSO)**.

With TSO on, the kernel doesn't cut outgoing TCP data into packets itself. It hands the NIC a chunk of up to 64 KB along with a header template, and the NIC's hardware splits it into about 45 packets that fit the 1500-byte MTU. That saves CPU, but the I219 sometimes trips over a chunk it's been asked to split and stops processing its transmit queue. Intel hasn't published a clear root cause, but years of bug reports agree that turning TSO off mostly makes it go away.

You'll often see **GSO (generic segmentation offload)** turned off alongside it in forum posts. GSO is the kernel's software version of the same idea: large chunks travel through the network stack as one unit, and the kernel splits them just before handing them to the driver. GSO never touches the NIC hardware, so it can't trigger this bug. With TSO off, GSO is what does the splitting, so I left it on.

My setup is pretty much the worst case for this bug. `eno2` isn't used directly. It's a port on a bridge (`br0`) that also carries a Home Assistant VM, plus a dozen or so Docker bridge networks and two NFS mounts from the NAS. That's a lot of large, mixed TCP traffic going out through one NIC.

### The fix

I wanted the change to survive reboots, so I made it in the NetworkManager profile that manages `eno2` instead of running `ethtool` by hand. On my machine, the profile is `br0-port`:

```bash
sudo nmcli con modify br0-port ethtool.feature-tso off
sudo nmcli con up br0-port
```

The first command saves the setting in the profile. NetworkManager can't change offload settings on a live device (`nmcli device reapply` fails with `Can't reapply any changes to 'ethtool' setting`), so the second command restarts the profile.

Worth noting that restarting the profile drops the network. Because `eno2` is a bridge port, the bridge goes through its spanning tree startup states (listening, then learning, then forwarding) before passing traffic again. For me that was about 30 seconds, which was long enough to drop my SSH session.

To check it worked:

```bash
$ ethtool -k eno2 | grep -E "^(tcp|generic)-segmentation-offload"
tcp-segmentation-offload: off
generic-segmentation-offload: on
```

The CPU cost is a few percent of one core when the link is running flat out at 1 Gbit/s, and throughput is the same.

If the hang comes back with TSO off, the next step is to turn off checksum offload as well with `ethtool.feature-tx off`.

### What I still don't know

I couldn't find what triggered the hang. In Beszel, I saw the load go from about 2 to 4 around 2 PM, and a spike in inbound network traffic around 2:20 PM. Nothing in the journal explains either:

- No timers, deployments, image pulls or container restarts between 2:00 and 2:19 PM.
- Immich, Syncthing and the Home Assistant VM didn't log anything.
- This bug is triggered by traffic the NIC _sends_, and a download mostly sends small acknowledgements back, which are too small to use TSO.

The inbound spike may well have started just after the hang at 2:19:07, which at Beszel's resolution would look like "around 2:20". And once the NFS mounts stopped responding, any process touching them would have blocked, which pushes the load average up. So some of what I saw in Beszel is probably the outage rather than its cause.

The machine doesn't keep per-process history, so that's where the trail went cold. If you want to be able to answer "what was using the CPU at 2 PM" next time, [atop](https://www.atoptool.nl/) with a one-minute logging interval might help, but this isn't something I've set up now.

I hope this helps.

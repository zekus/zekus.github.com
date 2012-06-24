---
date: '2007-09-27 17:22:45'
layout: post
slug: network-interface-problem-with-vmware-server
status: publish
title: Network interface problem with vmware server
wordpress_id: '75'
categories:
- Linux
---

So long time has passed from my last post... I've just been busy :/

Do you remember about the third part of vmware server installation never posted? Well I installed [Firestarter](http://www.fs-security.com/) as service and configured the firewall via the gui...

I'd have used IPTables directly, but the learing curve it's too high and I didnt had time for that because I was pressed by the work so, finally, I decided for this quick solution.

The server works like a charm, however ;)

I just had a bug to correct, and today, I had time to find a solution: automatically started virtual machines set to start connected in VMware Console, fail with following error (from log file):


> Could not get interface flags for vmnet1: No such device Virtual device Ethernet0 will start disconnected.


The problem is that vmnet1 adapter is slow initializing so vmware do it in background while continuing the boot process. If a VMware virtual machine is set to start automatically the vmnet1 adapter may not finish initializing in time, generating the error!


### Solution


```
sudo nano /usr/lib/vmware-server/net-services.sh
```
 locate the following line 
```
vmware_bg_exec 'Host-only networking on /dev/vmnet'"$vHubNr" \
```
 then substitute vmware_bg_exec with vmware_exec

This substitution let vmware wait vmnet adapter to be initialized instead of continuing with boot.

Now, the problem, should be solved ;)

ps. this bug is still present in VMWare server 1.0.3!

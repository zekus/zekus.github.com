---
comments: true
date: '2007-10-01 10:39:35'
layout: post
slug: strange-mac-address-change-on-ubuntu
status: publish
title: strange MAC address change on ubuntu
wordpress_id: '76'
categories:
- Linux
---

After the new kernel upgrade to 2.6.20-16-generic on the Ubuntu Server 7.04, I had a strage error after the reboot: no network device were found!
On a shell window, I restarted the network this way:


> sudo /etc/init.d/networking restart


that gave me following error:


> SIOCSIFADDR: No such device eth0
eth0: ERROR while getting interface flags: No such device


I was desperate and I started googling around till I found a an answer to this error that make me understand! Well I discovered that the problem is common and it depends from the mac address. The mac address has changed even if I haven't changed any hardware part!
In fact you can see that the current mac address
```
antonio@UbuntuServer:~$ dmesg | grep eth0
[   19.728029] eth0: VIA Rhine II at 0x1d000, 00:00:00:00:01:f8, IRQ 19.
```
 is not like the one stored in /etc/iftab
```
antonio@UbuntuServer:~$ cat /etc/iftab
# This file assigns persistent names to network interfaces.
# See iftab(5) for syntax.
```
 eth0 mac 00:13:d4:c6:4d:ec arp 1
then 00:00:00:00:01:f8 is not 00:13:d4:c6:4d:ec :) obviously!


### Solution


change the mac address in /etc/iftab with the new one and restart the machine (you cant just restart the networking service)

Hope you are smiling now ;)

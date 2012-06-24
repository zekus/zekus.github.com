---
date: '2008-01-17 17:10:44'
layout: post
slug: udev-change-peripheral-names
status: publish
title: udev change peripheral names
wordpress_id: '87'
categories:
- Linux
- vmware
tags:
- debian
- eth0
- ethernet
- ubuntu
- udev
- vmware
---

Often, in VMware Linux guests, it happens that the mac address of the virtual Ethernet card changes due to various operations I wont list here and, like in physical machines when you change the network card, the default Ethernet name changes from eth0 to eth1. If you want to restore the eth0 name, just edit the udev rule like this:
```
sudo nano /etc/udev/rules.d/70-persistent-net.rules
```
and change eth1 to eth0 minding to delete the row relative to the previous card (virtual or real) .

That's it!

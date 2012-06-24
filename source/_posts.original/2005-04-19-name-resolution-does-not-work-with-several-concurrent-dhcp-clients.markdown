---
date: '2005-04-19 18:04:00'
layout: post
slug: name-resolution-does-not-work-with-several-concurrent-dhcp-clients
status: publish
title: Name Resolution Does Not Work with Several Concurrent DHCP Clients
wordpress_id: '47'
categories:
- Linux
---

If you have some problems getting your wireless card work on startup and make you go on internet, READ THIS!
  

  
rapid solution ( in case you are lazy ):
  

  
Set the following option in the file ifcfg of all network devices configured as DHCP clients. This file is located at /etc/sysconfig/network/
  

  
_**DHCLIENT_PRIMARY_DEVICE=yes**_

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

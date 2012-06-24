---
date: '2005-10-18 02:07:00'
layout: post
slug: ipv6-problems-again
status: publish
title: ipv6 problems AGAIN
wordpress_id: '56'
categories:
- Linux
---

AGAIN since 9.1 version, ipv6 still break your internet connection, delaying DNS answere and giving the TIMEOUT ERROR!  
  
To disable this annoying thing, just edit /etc/modules.conf, go to the line containing "net-pf-10 ipv6" and change to "net-pf-10 off".  
Restart your machine and the world will smile again!  
  
happy suse!  
antonio

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

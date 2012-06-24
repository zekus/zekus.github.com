---
date: '2005-03-18 02:50:00'
layout: post
slug: apache2-settings
status: publish
title: Apache2 settings
wordpress_id: '42'
categories:
- Linux
---

after installing all needed rpms about apache2 and php4, just open /etc/apache2/httpd.conf and add following two lines on bottom to make UserDir and Alias work:  
Include /etc/apache2/mod_userdir.conf  
Include /etc/apache2/conf.d/*  
UserDir permit you to use /home//public_html directory as server directories and make users publish their own files.  
Alias permit to use any directory on you server for publish contents.  
For more infos, consult apache documentation or contact me!  
  
bye  
antonio

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

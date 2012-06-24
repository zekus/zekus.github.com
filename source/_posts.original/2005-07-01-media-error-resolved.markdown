---
date: '2005-07-01 20:51:00'
layout: post
slug: media-error-resolved
status: publish
title: /media error resolved
wordpress_id: '50'
categories:
- Linux
---

Have you got any problem wit /media directory? cannot automatically mount cd or usb drives? well, your solution is in fstab ( /etc/fstab ).  
Check if in fstab that media directory is mounted Read-Only ( ro ). If so, edit it and change ro with rw ( read-write ). Well, now you can umount /media/ and mount it again ( mount /media/ )!!  
  
well done  
  
bye  
antonio

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

---
comments: true
date: '2005-03-28 21:10:00'
layout: post
slug: backup-mysql-tables-and-restore
status: publish
title: backup mysql tables and restore
wordpress_id: '43'
categories:
- Linux
---

it's easy to backup all you mysql tables: just go to /var/lib/mysql (on SuSE linux distro) and copy all folders, that's it.  
If you record this forlders on a cd or dvd as backup and you lost all privilege settings, this is what you have to do after you copy back your backup on mysql folder:  
  
chmod -R 766 *  
chmod -R 700 mysql/  
  
and all will work fine again!  
  
go backup guys! ;)

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

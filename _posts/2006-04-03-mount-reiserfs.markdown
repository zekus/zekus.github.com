---
comments: true
date: '2006-04-03 13:01:00'
layout: post
slug: mount-reiserfs
status: publish
title: mount reiserfs
wordpress_id: '67'
categories:
- Linux
---

Well... I was gettin crazy with this so I decided to share the knowledge.  
I decided to add two new SATA hard drive to my friend's pc and configure a raid system.  
After creating the RAID via YaST I cant mount that via fstab to allow normal users read and write on that.  
Well, I was searchin a solution about options to add in fstab but that wasn't the right way. To do that just change permissions on the mounted drive and reiserfs will remeber that... EASY AS FUCK!  
  
summary:  
in /etc/fstab --->  
/dev/md0   /media/300gb  reiserfs  auto,users,user_xattr,exec  1 2  
<---  
  
777 permissions on mounted /media/300gb  
  
happy suse  
Antonio

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

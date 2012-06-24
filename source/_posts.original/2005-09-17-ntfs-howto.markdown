---
date: '2005-09-17 01:19:00'
layout: post
slug: ntfs-howto
status: publish
title: NTFS HowTO
wordpress_id: '53'
categories:
- Linux
---

Sometimes, in this world, it happen that you need to read from an NTFS partition with your fantastic SuSE 9.3 and you think it's easy to configure it with YaST -> patition ... and ... you find a bad surprise: IT DOESN'T WORK !!!!  
Don't disperate babe, you always have the command line ;) and my instructions!!!  
  
Open a shell and insert following commands:  


> mkdir /wherever/ntfs  
chown root:users /wherever/ntfs  
vim /etc/fstab

To the last line insert:  


> /dev/hda1  /wherever/ntfs  ntfs  ro,users,gid=users,umask=0002,nls=utf8  0  0

where "/dev/hda1" could be different according to your ntfs partition. Ex. "/dev/sda1" for USB disks.  
  
If yours it's an external HD write this:  


> /dev/sdb1 /wherever/ntfs subfs ro,users,uid=1000,gid=100,umask=0002,nls=utf8 0 0

  
where "/dev/sdb1" could be different on your system and uid/gid too. To verify uid/gid just type "id" in a shell and find your user.  
  
That's all folks!! Now you can mount your partition using "mount /dev/hda1"!!

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

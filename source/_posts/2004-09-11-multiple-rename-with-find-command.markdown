---
comments: true
date: '2004-09-11 21:21:00'
layout: post
slug: multiple-rename-with-find-command
status: publish
title: Multiple rename with find command!
wordpress_id: '33'
categories:
- Linux
---

I've done this shell script for multiple rename files not in same folder
  
(for doin that, simply use rename command) using the combination between mv and find in this way:
  


> for i in $(find / -name *.ext1);
  
do mv $i $(echo $i | cut -f1 -d.).ext2;
  
done

in the specific, this change an extension of a file (ext1) in one another (ext2).
  
feel free to modify it to match your needs.
  

  
bye
  


[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

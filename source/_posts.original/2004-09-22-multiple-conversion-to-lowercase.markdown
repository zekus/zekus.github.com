---
date: '2004-09-22 02:59:00'
layout: post
slug: multiple-conversion-to-lowercase
status: publish
title: multiple conversion to lowercase
wordpress_id: '35'
categories:
- Linux
---

This is a modified version of my script to change extensions, for lowercase (or uppercase inverting in script) multiple files in a directory recursively.
  


> for i in $(find . -type f);
  
do mv $i $(echo $i | tr "[:upper:]" "[:lower:]");
  
done


  
hope to be useful as usual.
  

  
good work!

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

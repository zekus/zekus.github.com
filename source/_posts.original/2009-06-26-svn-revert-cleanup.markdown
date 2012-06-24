---
date: '2009-06-26 13:17:27'
layout: post
slug: svn-revert-cleanup
status: publish
title: svn revert cleanup
wordpress_id: '222'
categories:
- shell
- SVN
tags:
- awk
- SVN
- xargs
---

You have reverted an svn merge and you have a lot of files not tracked (with exclamation mark, basically)?  
Clean it up:  
```
svn status | awk '$1 == "?" {print $2}' | xargs -t -i rm -r {}
```
  
Again, knowing awk and xargs turn helpful!  
  
  


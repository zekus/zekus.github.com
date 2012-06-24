---
date: '2008-05-12 11:32:45'
layout: post
slug: svn-log-filter-by-username-4
status: publish
title: 'svn log: filter by username'
wordpress_id: '100'
categories:
- Linux
- SVN
tags:
- sed
- SVN
---

I've found this command useful to filter the svn log by username:  
```
svn log | sed -n '/username/,/-----$/ p'
```
  
I hope is useful to anyone like it was for me ;)




ps. It's really useful to read the **sed** manual as well!

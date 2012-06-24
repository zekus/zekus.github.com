---
comments: true
date: '2008-05-30 11:06:52'
layout: post
slug: extract-portions-from-long-log-files
status: publish
title: Extract portions from long log files
wordpress_id: '102'
categories:
- Linux
tags:
- grep
- head
- log
- tail
---

Do you have a really long log file and you need to extract a portion from it?
Well, there are different approaches to this and it depends from what you really need from that file.
I'll show you the case where I need to extract a portion of y lines from an x line number :



	
  1. **get the line number**
to get the line number, if you don't know it already, use grep and a pattern
```
grep -n _pattern_ /var/log/examplelogfile
```

	
  2. **extract the portion**
use head to output the first 200 lines and use tail to take 100 lines starting from the bottom
```
head -n 200 /var/log/examplelogfile | tail -n 100
```


In this case, I extracted the portion from line 100 to line 200. In other words, I've taken 100 lines starting from line 100.
I hope I've been clear enough!

ps. thanks to my colleague Mauro for the second part of this trick.

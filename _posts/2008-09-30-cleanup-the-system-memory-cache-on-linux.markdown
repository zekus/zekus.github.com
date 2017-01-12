---
comments: true
date: '2008-09-30 15:22:14'
layout: post
slug: cleanup-the-system-memory-cache-on-linux
status: publish
title: Cleanup the system memory cache on linux
wordpress_id: '129'
categories:
- Altro
tags:
- cache
- clean
- Linux
- memory
---

what is that? you have done digited free in you linux shell and you see that all the memory is fulfilled by the cache?

```
sudo -s
sync; echo 3 > /proc/sys/vm/drop_caches
```

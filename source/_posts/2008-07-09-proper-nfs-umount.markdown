---
comments: true
date: '2008-07-09 12:39:53'
layout: post
slug: proper-nfs-umount
status: publish
title: proper nfs umount
wordpress_id: '112'
categories:
- Linux
- shell
tags:
- bash
- Linux
- nfs
- shell
---

Hi

if you try to umount an NFS mountpoint this way
```
root:~> umount /mountpoint
```
and your shell answer this way
```
umount: /mountpoint: device is busy
umount: /mountpoint: device is busy
```
then try killing all processes using the mountpoint and update the nfs export fs
```
root:~> fuser -k -m /mountpoint
root:~> exportfs -au
```
at this point, you can safely umount
```
root:~> umount /mountpoint
```

peace!

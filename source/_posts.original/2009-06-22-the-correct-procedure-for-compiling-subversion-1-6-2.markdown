---
date: '2009-06-22 10:44:35'
layout: post
slug: the-correct-procedure-for-compiling-subversion-1-6-2
status: publish
title: the correct procedure for compiling subversion 1.6.2
wordpress_id: '216'
categories:
- Linux
- SVN
---

Not sure if this is the complete way of doing it (I'm not telling you which .deb to install), but it worked for me:  
  
Remove some waste from eventual previous compilations:  
```
  
$ rm -rf /usr/loca/lib/libsvn*  
$ rm -rf /usr/local/lib/libapr*  
$ rm -rf /usr/local/lib/libexpat*  
$ rm -rf /usr/local/lib/libneon*  
```
  
Run autogen  
```
  
$ ./autogen.sh   
```
  
Configure and install (it is important to follow the order)  
```
  
$ ./configure  
$ make -j external-all  
$ make -j local-all  
$ sudo make install  
```
  
That's it. Hope to have helped someone as usual.  
  


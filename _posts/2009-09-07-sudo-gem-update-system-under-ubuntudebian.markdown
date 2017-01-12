---
comments: true
date: '2009-09-07 12:35:08'
layout: post
slug: sudo-gem-update-system-under-ubuntudebian
status: publish
title: sudo gem update --system under ubuntu/debian
wordpress_id: '243'
categories:
- Altro
---

If you have tried that command, you already know that doesn't work!  
Here is the correct procedure to update gem under ubuntu/debian without using apt-get/aptitude  
```
  
$ sudo gem install rubygems-update  
$ cd /var/lib/gems/1.8/bin  
$ sudo ./update_rubygems  
$ gem -v  
$ 1.3.5  
```
  
Happy rubying :)

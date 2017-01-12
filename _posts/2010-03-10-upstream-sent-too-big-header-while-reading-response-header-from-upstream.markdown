---
comments: true
date: '2010-03-10 17:21:46'
layout: post
slug: upstream-sent-too-big-header-while-reading-response-header-from-upstream
status: publish
title: upstream sent too big header while reading response header from upstream
wordpress_id: '331'
categories:
- Linux
- nginx
- PHP
tags:
- buffer
- fastcgi
- nginx
- PHP
- php-fpm
---

if you have this error from nginx with php-fpm and output_buffers = On in your php.ini then try to increment the buffer size in nginx:  
```
  
fastcgi_buffers 8 16k;  
fastcgi_buffer_size 32k;  
```
  
  




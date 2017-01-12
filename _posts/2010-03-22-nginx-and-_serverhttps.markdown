---
comments: true
date: '2010-03-22 17:50:06'
layout: post
slug: nginx-and-_serverhttps
status: publish
title: Nginx and $_SERVER['HTTPS']
wordpress_id: '337'
categories:
- nginx
- PHP
---

When you are using the FastCGI Php version, you would set HTTPS variable if you are serving parts of you website with SSL.
To do that, add the following function into the http section of your nginx configuration
```
map $scheme $fastcgi_https { ## Detect when HTTPS is used
default off;
https on;
}
```
and use the variable into your server section
```
fastcgi_param  HTTPS $fastcgi_https;
```

Lazy explanation as usual :P




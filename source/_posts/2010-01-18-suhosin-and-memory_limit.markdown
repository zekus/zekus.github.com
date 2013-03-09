---
comments: true
date: '2010-01-18 13:00:29'
layout: post
slug: suhosin-and-memory_limit
status: publish
title: Suhosin and memory_limit
wordpress_id: '313'
categories:
- PHP
tags:
- ini_set
- PHP
- suhosin
---

I had some problem with a script that needed more memory to be executed and was using **ini_set('memory_limit', '50M').** For some reasons the memory was not incremented as expected.  
After googleing around for a solution I just had an intuition: could be _suhosin_? Indeed, the problem was in the _suhosin_ module that is enable by default on Ubuntu: it does not allow to redefine the memory limit over the limit specified in the php.ini file.  
To make ini_set work normally under Ubuntu, comment out the __suhosin__ extension in _/etc/php5/apachew/conf.d/suhosin.ini_  
  
;)  
  


![](http://img.zemanta.com/pixy.gif?x-id=49530aa3-b720-8bdb-8012-a9ae94d8b5ab)

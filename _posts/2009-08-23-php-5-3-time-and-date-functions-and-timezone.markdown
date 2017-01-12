---
comments: true
date: '2009-08-23 01:55:52'
layout: post
slug: php-5-3-time-and-date-functions-and-timezone
status: publish
title: 'php 5.3, time and date functions and timezone '
wordpress_id: '233'
categories:
- PHP
tags:
- '5.3'
- date
- PHP
- time
- timezone
---

After installing PHP 5.3, you may get a warning for every function involving date and time like
```
Warning: strtotime() [function.strtotime]: It is not safe to rely on the system's timezone settings. You are *required* to use the date.timezone setting or the date_default_timezone_set() function. In case you used any of those methods and you are still getting this warning, you most likely misspelled the timezone identifier. We selected 'Europe/London' for [...]
```
To fix this, you can set the timezone in your script using **[date_default_timezone_set('Europe/London');](http://uk.php.net/manual/en/function.date-default-timezone-set.php)** or set it into the php.ini file with **[date.timezone = 'Europe/London'](http://uk.php.net/manual/en/datetime.configuration.php#ini.date.timezone)**

;)



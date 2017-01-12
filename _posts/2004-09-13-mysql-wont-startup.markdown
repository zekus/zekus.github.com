---
comments: true
date: '2004-09-13 16:46:00'
layout: post
slug: mysql-wont-startup
status: publish
title: MYSQL wont startup
wordpress_id: '34'
categories:
- Linux
---

Today, mysql wont startup and dont know why (or maybe!)
  
First of all I looked at "/var/lib/mysql/<\your host name\>.err" log and this was the error:
  


> Fatal error: Can't open privilege tables: Can't find file: 'host.MYI' (errno: 2)
  


The problem is the file was there (/var/lib/mysql/mysql).
  
The solution is delete /var/lib/mysql/mysql wit command rm -fR,
  
type rcmysql start and the folder will be recreated.
  
You'll lost all users but mysql will be up and running! Now you have to reset the root password: mysqladmin -u root password
  

  
hope to have been useful again!
  

  
P.S.
  
I forgot... the error was my fault ... I played too much with phpmyadmin.
  
Machines do always what we want they do!
  


[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

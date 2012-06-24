---
date: '2005-01-24 18:07:00'
layout: post
slug: force-user-logout
status: publish
title: Force user logout!
wordpress_id: '39'
categories:
- Linux
---

have you ever wanted to know how to force logout of a user on a remote machine that is logged in locally ( or remotely too :P )?
  

  
here the tip:
  


> kill -15 $(ps -U NameOfUserToLogout -o "pid=")


  
what does it mean this command??
  
well why dont you type in your command line these other two commands:
  


> man kill
  
man ps


  
you will learn more, guaranteed :D
  

  


[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

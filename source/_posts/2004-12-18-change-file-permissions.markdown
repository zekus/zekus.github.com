---
comments: true
date: '2004-12-18 19:36:00'
layout: post
slug: change-file-permissions
status: publish
title: change file permissions
wordpress_id: '38'
categories:
- Linux
---

Again a simple command to simplefy our life on linux/unix machines :D
  

  
As you know I am a webmaster and usually I need to upload files on webservers that manage permissions in different ways from me on my machine and I have to chmod a large amount fo files. Using following command I can make this work in seconds :D
  


>    find . -type d -name public_html -exec chmod 0755 {} \;
  


It searches (using find recursively (ie it checks folders and sub folders/directories and sub directories) for a directory (-type d) called (-name) public_html and when it does it runs the command (-exec) chmod 0755 (which sets the permissions so that the owner can read, write and execute/open the folder and all other users can read and execute/open the folder).
  

  
Feel free to experiment and change this command on your machine
  

  
bye

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

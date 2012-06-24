---
comments: true
date: '2006-03-07 15:41:00'
layout: post
slug: flock-simply-human
status: publish
title: Flock ... simply human ;)
wordpress_id: '9'
categories:
- Linux
---

Flock is a Mozilla Firefox-based web browser not yet officially out, but is available as a developer’s preview.  
This guide will help you, running Ubuntu, to install Flock.  
First, run over to [http://www.flock.com/developer/linux.php](http://www.flock.com/developer/linux.php) and download the latest version of Flock in your home directory for easy explaination.  
 In this installation we’re going to be using Flock 0.5.12.  
Open up your terminal and use the following string of commands:  
  


> cd /opt  
sudo tar -xzvf /home/yourname/flock-0.4.10.en-US.linux-i686.tar.gz  
sudo ln -s /opt/flock/flock /usr/bin/flock

Now you’ve successfully installed Flock, but you want to add it to your Ubuntu Applications menu!

>  sudo gedit /usr/share/applications/flock.desktop

  


Now, add the following to the new file:

> [Desktop Entry]  
Encoding=UTF-8  
Name=Flock Browser  
 Comment=Flock Browser  
 Exec=/opt/flock/flock %u  
 Terminal=false  
 MultipleArgs=false  
 Type=Application  
 Icon=/opt/flock/icons/mozicon128.png  
 Categories=Application;Network  
 MimeType=text/html; text/xml; application/xhtml+xml; application/xml; application/vnd.mozilla.xul+xml; application/rss+xml; application/rdf+xml;x-directory/webdav; x-directory/webdav-prefer-directory; image/gif; image/jpeg; image/png

     


After that, You should see Flock in your applications menu under ‘Internet’  

   

 Have Fun    
 Antonio   

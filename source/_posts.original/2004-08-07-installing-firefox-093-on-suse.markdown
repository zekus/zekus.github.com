---
date: '2004-08-07 21:13:00'
layout: post
slug: installing-firefox-093-on-suse
status: publish
title: installing firefox 0.9.3 on suse
wordpress_id: '20'
categories:
- Linux
---

First of all I need my dear web browser mozilla Firefox so I download the official version from [mozilla project](http://www.mozilla.org/firefox/) and the language pack from [italian mozilla project.](http://www.mozillaitalia.org/)
  
After downloading I switch to root, decompress the file in /opt/firefox/ and doublecliccked on installer.
  
OK all seam allright... now I have to click on firefox and ... It doesn't work! SIGH!! ='[
  
well ... I can do it! I launch firefox from shell so I can see messages and resolve the problem:
  

  
Xlib:connection to ":0.0" refused by server
  
Xlib:XDM authorization key matches an existing client!
  
(firefox-bin:13607):Gtk-WARNING ** cannot open display
  

  
AAAAAAAAAAAAAHHHHHHHHHHHHH!!!
  
what should I do now?
  
let's do a google search and... bingo! here the solution!
  
I switch back to user and open a shell where I write:
  

  
su -m
  
password:
  
xhost + (switch off X authorization)
  
/opt/firefox/firefox-installer/firefox
  
et voilà! les jeux sont fait! (dont write this line on shell =D)
  
xhost - (switch on X authorization)
  

  
next operations: language pack and flash player!
  

  
gotta go! bye...
  


[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

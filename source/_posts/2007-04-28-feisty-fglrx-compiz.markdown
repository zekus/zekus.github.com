---
comments: true
date: '2007-04-28 23:00:00'
layout: post
slug: feisty-fglrx-compiz
status: publish
title: Feisty fglrx compiz
wordpress_id: '15'
categories:
- Linux
---

Easy Desktop Effects ( Compiz ) on Feisty Fawn!  
  
If you have FGLRX drivers, just...   


  * install xserver-xgl from the official ubuntu repository
  * disable AIGLX and Composite extension in xorg.conf  


> Section "ServerFlags"  
       Option  "AIGLX" "off"  
EndSection  
  
Section "Extensions"  
      Option "Composite" "Disable"  
EndSection

  * make a script to start xgl cutting and pasting following script in /usr/bin/startxgl  


> #!/bin/sh   
Xgl :1 -fullscreen -ac -accel xv:pbuffer -accel glx:pbuffer &  
DISPLAY=:1  
exec dbus-launch --exit-with-session gnome-session

  * make the script executable  


> sudo chmod +x /usr/bin/startxgl

  * make a session menu entry in GDM cutting and pasting following code in /usr/share/xsessions/xgl.desktop  


> [Desktop Entry]  
Encoding=UTF-8  
Name=Xgl  
Comment=Start an Xgl Session  
Exec=/usr/bin/startxgl  
Icon=  
Type=Application

  * restart session and choose xgl from the gdm session menu
  * activate desktop effects from System-&gt;Preference-&gt;Desktop Effects
  * resolve the bug of the cube cutting and pasting this commands in a terminal  


> gconftool-2 --type int --set /apps/compiz/general/screen0/options/hsize 4  
gconftool-2 --type int --set /apps/compiz/general/screen0/options/number_of_desktops 1

That's it!

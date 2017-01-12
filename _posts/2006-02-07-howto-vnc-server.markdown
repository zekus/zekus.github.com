---
comments: true
date: '2006-02-07 16:49:00'
layout: post
slug: howto-vnc-server
status: publish
title: howto vnc server
wordpress_id: '4'
categories:
- Linux
---

1. Enable XDMCP  


> System->Administration->Login Screen Setup  
Tab Security->Enable XDMCP  


  
2. Install required packages (vncserver and xinetd)  


>   
sudo apt-get install vnc4server xinetd

  
3. Set the VNC passwd  


> sudo vncpasswd /root/.vncpasswd

  
4. Add vnc service to xinetd:  


>   
sudo gedit /etc/xinetd.d/Xvnc

  
Enter this into the new file:  


> service Xvnc1   
{   
type = UNLISTED   
disable = no   
socket_type = stream   
protocol = tcp   
wait = yes   
user = root   
server = /usr/bin/Xvnc   
server_args = -inetd :1 -query localhost -geometry 1024x768 -depth 16 -once -fp /usr/share/X11/fonts/misc passwordFile=/root/.vncpasswd   
port = 5901   
}

  
For more than one vnc session, duplicate the code above incrementing the screen number and the port as in the code below  


> service Xvnc1   
{   
type = UNLISTED   
disable = no   
socket_type = stream   
protocol = tcp   
wait = yes   
user = root   
server = /usr/bin/Xvnc   
server_args = -inetd :1 -query localhost -geometry 1024x768 -depth 16 -once -fp /usr/share/X11/fonts/misc passwordFile=/root/.vncpasswd   
port = 5901   
}  
  
service Xvnc2   
{   
type = UNLISTED   
disable = no   
socket_type = stream   
protocol = tcp   
wait = yes   
user = root   
server = /usr/bin/Xvnc   
server_args = -inetd :2 -query localhost -geometry 1024x768 -depth 16 -once -fp /usr/share/X11/fonts/misc passwordFile=/root/.vncpasswd   
port = 5902   
}  
  
service Xvncn   
{   
type = UNLISTED   
disable = no   
socket_type = stream   
protocol = tcp   
wait = yes   
user = root   
server = /usr/bin/Xvnc   
server_args = -inetd :n -query localhost -geometry 1024x768 -depth 16 -once -fp /usr/share/X11/fonts/misc passwordFile=/root/.vncpasswd   
port = 590n   
}  


  
5. Restart xinetd (usually there is no need to reboot, but occasionally it might be required)  


>   
sudo /etc/init.d/xinetd stop   
sudo killall Xvnc   
sudo /etc/init.d/xinetd start

  
6. That's it! To test that this is working first try to connect from the same machine (the machine we just set up the VNC server on):  


> vncviewer localhost:1

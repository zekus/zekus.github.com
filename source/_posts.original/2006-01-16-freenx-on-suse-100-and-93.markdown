---
date: '2006-01-16 23:05:00'
layout: post
slug: freenx-on-suse-100-and-93
status: publish
title: FreeNX on SuSE 10.0 and 9.3
wordpress_id: '64'
categories:
- Linux
---

Well... FreeNX is the best remote controlling system now on earth and pretty easy to install on our Suse distro.  
  
Just open YaST and search for freenx and select all related packets.  
  
Do you think it's enoght? the answer that you are waitin for it's NO :D  
  
[I put here a link of a well done tutorial on MadPenguin.org](http://madpenguin.org/cms/index.php/?m=show&id=5755&page=1) ( cause, you know, I'm lazy :P )  
  
And for you that dont understand why you cant still connect after this tutorial, here is the troubleshoot:  
  
Error message Server not installed or NX access disabled   
  
If you see the following error message it means that the nx user's public key was not accepted.:   
  
NX> 203 NXSSH running with pid: 6721  
NX> 285 Enabling check on switch command  
NX> 285 Enabling skip of SSH config files  
NX> 200 Connected to address: 192.168.2.21 on port: 22  
NX> 202 Authenticating user: nx  
NX> 208 Using auth method: publickey  
NX> 204 Authentication failed.  
This can be caused by a couple of things.   
  
the nx user's authorized key file /var/lib/nxserver/home/.ssh/authorized_keys2 is incorectly named. All versions of ssh that I have seen on Ubuntu, Fedora, Redhat/Centos and OFCOURSE suse are configured to look for an authoized key file names .ssh/authorized_keys not .ssh/authorized_keys2. You can rename the authorized_keys file but it might be better to reconfigure sshd_config because the nxserver --stop command renames the .ssh/authorized_keys2 to .ssh/authorized_keys2.disabled to prevent access via an nxclient   
sshd is not running or is incorrectly configured. At minimum you need PubkeyAuthentication yes in the sshd_config file   
The server and client public keys might be different. At install the server and client use a default key which should be changed. You can open /var/lib/nxserver/home/.ssh/authorized_keys and compare its contents to the key stored in the client by:   
Open the client tool   
Click the Configure button   
Click the Key button on the General Tab   
Ensure that the key matches the key found in /var/lib/nxserver/home/.ssh/authorized_keys on the server  
  
Enjoy FreeNX, enjoy openSuSE  
  
Antonio

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

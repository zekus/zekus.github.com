---
date: '2005-12-06 18:16:00'
layout: post
slug: cups-and-hotplug
status: publish
title: CUPS and HOTPLUG
wordpress_id: '62'
categories:
- Linux
---

This is a really short HOWTO to configure hotplug to auto-enable usb printer on pluggin in :)  
  
1) lsusb -v show, if printer is plugged in, his ID and VENDOR.  
  
2) create file printer.usermap in /etc/hotplug/usb/  
Here we will paste this :  


> printer  0x0003  0x[yourprinterid]  0x[yourprintervendorid]  0x0000  0x0000  0x00  0x00  0x00  0x00  0x00  0x00  0x00000000

3) create file printer in /etc/hotplug/usb/  
Here create the script like this example that enable and accept jobs for a printer:  


> #!/bin/bash  
  
if [ "${ACTION}" = "add" ]  
then  
  lpadmin -p _printername_ -E  
fi

4) dont forget to chmod the file to make it executable :)  
  
happy hotpluggin  
antonio

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

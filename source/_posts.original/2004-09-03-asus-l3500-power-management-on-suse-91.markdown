---
date: '2004-09-03 18:16:00'
layout: post
slug: asus-l3500-power-management-on-suse-91
status: publish
title: Asus L3500 Power Management on SuSE 9.1
wordpress_id: '29'
categories:
- Linux
---

Today, I discovered that power management on my asus doesn't function properly and that I can configure extra buttons and leds on my laptop trought powersave (default acpi manager for suse).
  
Now I'll show you how-to do it!
  

  
SUSPEND AND STANDBY
  


> edit **'/etc/powersave.conf'**. Right at the end there are two lines:
  
POWERSAVED_DISABLE_USER_SUSPEND=yes							POWERSAVED_DISABLE_USER_STANDBY=yes
  
modify it to 'no'


  
ASUS_ACPI
  


> acpi4asus (kernel module for asus special keys and leds) is included in the kernel (from 2.6). Just load the module 'asus_acpi' since startup, editing the file '/etc/sysconfig/powersave/common'.
  

  
Search for the definition of 'POWERSAVE_ACPI_MODULES' and add 'asus_acpi'.
  
Same goes for 'POWERSAVE_ACPI_MODULES_NOT_TO_UNLOAD'.
  

  
Set POWERSAVE_CPUFREQD_MODULE="p4-clockmod" (doesnt work well: cpu boot at 300Mhz instead of 2.400Mhz even I've set powersave as well! tryin to find help and further informations)
  



  
searching for other tips... stay tuned!
  



  
sources:
  
[http://www.wach-o-witz.de/asus_l3500d_install.html](http://www.wach-o-witz.de/asus_l3500d_install.html)
  


[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

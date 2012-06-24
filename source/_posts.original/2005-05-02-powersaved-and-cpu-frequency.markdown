---
date: '2005-05-02 20:49:00'
layout: post
slug: powersaved-and-cpu-frequency
status: publish
title: Powersaved and CPU frequency
wordpress_id: '48'
categories:
- Linux
---

Sometimes, powersaved daemon, cannot recognize cpu correctly and load the necessary cpufreq module. To force loading of module concerning your CPU, modify **/etc/sysconfig/powersave/cpufreq** file adding the module to the voice **POWERSAVE_CPUFREQD_MODULE=""**.
  
  

  
Full list of available modules could be find [here](http://www.kernel.org/pub/linux/utils/kernel/cpufreq/hardware.html)
  


[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

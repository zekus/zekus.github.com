---
comments: true
date: '2004-09-07 17:24:00'
layout: post
slug: tips-installing-software-on-suse-91
status: publish
title: Tips Installing software on SuSE 9.1
wordpress_id: '31'
categories:
- Linux
---

To install RPM files with Yast from command line, type this : yast -i <\packagetoinstall\>.rpm
  

  
If you downloaded source code from a program (tar.gz files) you can quickly make an RPM file from it.
  
To do this, first of all install the package "checkinstall", then unpack your source package and cd to the directory where you unpacked the tar.gz file.
  
Run the following commands:
  

  
./configure
  
make
  
checkinstall #instead of make install
  

  
When finished, you'll find your RPM in /usr/src/packages/RPMS/i686
  

  
Now you can install it where you want with yast - i <\packagetoinstall\>.rpm or with rpm -i <\packagetoinstall\>.rpm. This allows your to easily uninstall it afterwards.
  

  
bye

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

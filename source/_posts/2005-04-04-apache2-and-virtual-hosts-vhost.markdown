---
comments: true
date: '2005-04-04 21:37:00'
layout: post
slug: apache2-and-virtual-hosts-vhost
status: publish
title: Apache2 and Virtual Hosts (VHost)
wordpress_id: '44'
categories:
- Linux
---

In this article, i'll explain you how to set your Apache configuration on SuSE 9.2 to make your local websites visible on you machine. This is particularly useful for people like me who make websites and need to test them on their local machines before publish.  
  
First of all, you need Apache installed on you machine via YaST with eventually PHP and MySql.  
After that you'll have all apache configuration files under /etc/apache2 directory.  
Well DONT TOUCH ANY FILE THERE!  
The simplest thing you have to do is create a mysites.conf file wherever you want and hardlink it to /etc/apache2/vhosts.d  
I created mysites.conf in my public_html for my personal comfort :)  
  
What about mysites.conf content? HERE to you a simple example:  


>   
  
NameVirtualHost *  
  
<virtualhost>  
ServerName localhost  
ServerAlias linzekus  
DocumentRoot /srv/www/htdocs  
</virtualhost>  
  
<virtualhost>  
DocumentRoot /home/zekus/public_html/ontosofia/ontosophy  
ServerName ontosophy  
ServerAdmin antonio@linzekus  
</virtualhost>  
  


  
Thus, the last thing to do is adding all our virtual servers on /etc/hosts file to make them available. This file is only accessible via root and this is a sample:  


>   
#  
# hosts         This file describes a number of hostname-to-address  
#               mappings for the TCP/IP subsystem.  It is mostly  
#               used at boot time, when no name servers are running.  
#               On small systems, this file can be used instead of a  
#               "named" name server.  
# Syntax:  
#  
# IP-Address  Full-Qualified-Hostname  Short-Hostname  
#  
  
127.0.0.1       localhost linzekus XXXX <-list all virtual hosts HERE  
# special IPv6 addresses  
::1  localhost ipv6-localhost ipv6-loopback  
fe00::0         ipv6-localnet  
ff00::0         ipv6-mcastprefix  
ff02::1         ipv6-allnodes  
ff02::2         ipv6-allrouters  
ff02::3         ipv6-allhosts  


  
What else now? Point your browser on the URL of your new virtual hosts like that:  
  


http://xxxx  


  
Thats all folks!  
good setting

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

---
comments: true
date: '2005-12-03 15:49:00'
layout: post
slug: virtual-nameservers
status: publish
title: virtual nameservers
wordpress_id: '61'
categories:
- Linux
---

Maybe nobody need these informations if not interested in webserver management :)
  

  
Virtual nameservers:
  
I'm pointing my nameservers to the IPs of my webhost's nameservers.  So it sounds like 'virtual' is the correct term.  Using your example,
  
ns1.mydomain.com => IP of dnsmyhoster.com's DNS server #1
  
ns2.mydoman.com => IP of dnsmyhoster.com's DNS server #2
  

  
Step 1.  Create the nameservers at the registrar (contact your registrar if you dont have direct access).
  
  NS1.mydomain.com => IP#1
  
  NS2.mydomain.com => IP#2
  

  
Step 2.  Create the nameservers at the host.
  
It currently looks like this:
  
  example.com.  =>  ns1.dnsmadeeasy.com.  (type: NS)
  
  example.com.  =>  ns2.dnsmadeeasy.com.  (type: NS)
  
Should be changed like this:
  
  example.com.  =>  ns1.example.com.  (type: NS)
  
  example.com.  =>  ns2.example.com.  (type: NS)
  

  
Step 3.  Add A records on the authoritative DNS servers at the host.
  
This looks easy enough.
  
  ns1.example.com.  =>  IP#1  (type: A record)
  
  ns2.example.com.  =>  IP#2  (type: A record)
  

  
happy hosting
  
antonio

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

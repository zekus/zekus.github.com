---
date: '2005-11-24 03:46:00'
layout: post
slug: d-link-dns-bugs-on-dsl-g604t-and-similar-shit
status: publish
title: d-link dns bugs on DSL-G604T and similar SHIT
wordpress_id: '60'
categories:
- Linux
---

Well, this is the second bug (the first was ipv6) I've found on this stupid router (like all d-link stuff) that made me crazy...
  

  
Some applications are unable to resolve domains (such as wget, lynx and whois in my case) and I didn't knew why until I changed the default nameserver (the router address from dhcp) on /etc/resolv.config to the ones gave from my ISP: ALL MAGICALLY WORKS NOW (FUCK!!!)
  

  
If you don't like dhcpcd to change your nameserver settings then either set DHCLIENT_MODIFY_RESOLV_CONF=no in /etc/sysconfig/network/dhcp, or set MODIFY_RESOLV_CONF_DYNAMICALLY=no in /etc/sysconfig/network/config or (manually) use dhcpcd with -R.  If you only want to keep your searchlist, set DHCLIENT_KEEP_SEARCHLIST=yes in /etc/sysconfig/network/dhcp or (manually) use the -K option.
  

  
see you
  
antonio

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

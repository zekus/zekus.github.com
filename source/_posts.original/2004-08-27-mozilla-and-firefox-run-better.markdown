---
date: '2004-08-27 11:51:00'
layout: post
slug: mozilla-and-firefox-run-better
status: publish
title: mozilla and firefox run better
wordpress_id: '27'
categories:
- Linux
---

Take Note: These tips are for SUSE 9.1 with the 2.6 kernel:              

![Suse 9.1 with 2.6 kernel tips](http://www.thelinuxapprentice.com/images/ipv6fixsm.gif)Mozilla and FireFox both seem to run a little slow on Suse 9.1 cause "ipv6". What is "ipv6"...sheee...I haven't a clue...but there is a fix...and after I applied it...both Mozilla 1.7 rc1 and FireFox opened and went to the different websites fast. Before the fix...both browsers would often just sit and spin their little icons...and never reach the sites before they timed out. 

              

  * Fix One: Go to >> /etc/modprobe.conf, right below this                  line:
  
              alias net-pf-10 ipv6
  
              add the following line:
  
              install ipv6 /bin/true
  
Found this fix on Yahoo SCOX Message Board and credit for fix goes to w4rmc47, who posts on yahoo finance scox message board.

  

  
source : [thelinuxapprentice](http://www.thelinuxapprentice.com/)

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

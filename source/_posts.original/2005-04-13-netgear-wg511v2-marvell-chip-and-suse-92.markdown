---
date: '2005-04-13 02:11:00'
layout: post
slug: netgear-wg511v2-marvell-chip-and-suse-92
status: publish
title: NETGEAR WG511v2 (Marvell chip) and SuSE 9.2
wordpress_id: '46'
categories:
- Linux
---

Ladies and Gentlemen,  
we are here reunited to celebrate the fantastic NDISWRAPPER and his team for make wireless work on our linux boxes and my SuSE Laptop too :)  
Let's go to show how to make this fuckin pcmcia card to work (Gates slaves!!).... ohhhhhh shit, I dont wanna write now, it's late! it's 2:11 am and I'm sitting on a wc, havin my shit (yeeeessss i'm really on wireless, yeeeeeah!) and wanna go sleep soon so, check out this two links:  
  
[http://ndiswrapper.sourceforge.net/phpwiki/index.php?Installation](http://ndiswrapper.sourceforge.net/phpwiki/index.php?Installation)   
(HArd but worked for me!)  
[http://ndiswrapper.sourceforge.net/phpwiki/index.php/Suse%20Professional%209.2](http://ndiswrapper.sourceforge.net/phpwiki/index.php/Suse%20Professional%209.2)   
(didnt work for netgear)  
  
you can mix up the two articles and you will be wireless soon!  
maybe next time I'll make a summary mix for you.  
  
bye  
antonio  
  
TIP:  
if you get an error loading the module ndiswrapper (moprobe ndiswrapper), do this:  
rm /lib/modules/$(uname -r)/extra/ndiswrapper.ko  
cp /lib/modules/$(uname -r)/misc/ndiswrapper.ko /lib/modules/$(uname -r)/extra

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

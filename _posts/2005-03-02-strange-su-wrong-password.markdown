---
comments: true
date: '2005-03-02 18:57:00'
layout: post
slug: strange-su-wrong-password
status: publish
title: strange SU wrong password
wordpress_id: '41'
categories:
- Linux
---

Haven't told you that I've installed the brand-new SuSE 9.2 on my laptop and It works great only if I use KDE. In fact I tried Gnome 2.6 and was so unhappy to see that it doesn't work good... Gnome it's hard to configure if u are a maniac of personalization. Let me know if your experience wit gnome have been better than mine!  
  
But, let's talk about the title's argument. It was so strange but, after a long "play" with yast and user configuration, I wasn't able to "su" or "sudo" from console. Still dont know what happened but that executables lost the suid privileges. What I've done, to make all things work again, was:  
  
chown 4755 /bin/su /usr/bin/sudo  
  
bye

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

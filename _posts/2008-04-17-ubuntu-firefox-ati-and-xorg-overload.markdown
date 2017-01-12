---
comments: true
date: '2008-04-17 11:50:20'
layout: post
slug: ubuntu-firefox-ati-and-xorg-overload
status: publish
title: Ubuntu, Firefox, ATI and xorg overload
wordpress_id: '95'
categories:
- Linux
tags:
- ati
- firefox
- ubuntu
- xorg
---

I was stuck with firefox and xorg on my Ubuntu machine: it was so slooooow. Today, finally, I've found a solution: just add the following option to your xorg.conf file under the device section:
```
Option "XAANoOffscreenPixmaps" "true"
```
then reboot your machine or your xorg server only (ctrl-alt-backspace) and ...

breath deeply :O

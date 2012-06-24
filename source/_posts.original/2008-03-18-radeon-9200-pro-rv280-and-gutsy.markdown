---
date: '2008-03-18 10:25:24'
layout: post
slug: radeon-9200-pro-rv280-and-gutsy
status: publish
title: Radeon 9200 PRO (rv280) and Gutsy
wordpress_id: '92'
categories:
- Linux
tags:
- gutsy
- Linux
- radeon 9200
- rv280
- ubuntu
- xorg
---

I've just solved a problem with dual head at work and I want to share this.
The "man" that gave me a hand was [here](http://blogs.gnome.org/jamesh/2007/09/24/gutsy-upgrade/) and thaks to him, this is my working xorg.conf configuration:
```
Section "Device"
Identifier      "ATI Technologies Inc RV280 [Radeon 9200 PRO]"
Driver          "ati"
BusID           "PCI:3:2:0"
Option          "monitor-DVI-0" "Dell E176FP"
Option          "monitor-VGA-0" "Dell E196FP"
EndSection
Section "Monitor"
Identifier      "Dell E196FP"
Option          "DPMS"
HorizSync       31-83
VertRefresh     56-76
EndSection
Section "Monitor"
Identifier      "Dell E176FP"
Option          "DPMS"
HorizSync       31-80
VertRefresh     56-75
Option          "RightOf"        "Dell E196FP"
EndSection
Section "Screen"
Identifier      "Default Screen"
Device          "ATI Technologies Inc RV280 [Radeon 9200 PRO]"
Monitor         "Dell E196FP"
DefaultDepth    16
SubSection "Display"
Modes           "1280x1024" "1024x768" "800x600" "640x480"
Virtual         2560 1024
EndSubSection
EndSection
```

Modify it to fits your needs. Cheers to my collegues that tried to help me too ;)

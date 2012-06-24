---
date: '2007-04-30 09:32:00'
layout: post
slug: make-xgl-and-powerplay-working
status: publish
title: Make Xgl and PowerPLAY work
wordpress_id: '16'
categories:
- Linux
---

I discovered, googling around, following commands to query and set powerstate when Xgl is running:


> DISPLAY=:0 aticonfig --lsp
DISPLAY=:0 aticonfig --set-powerstate=3
DISPLAY=:0 aticonfig --set-powerstate=1


Happy to share it with you!

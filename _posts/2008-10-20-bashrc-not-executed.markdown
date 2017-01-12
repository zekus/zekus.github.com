---
comments: true
date: '2008-10-20 11:55:34'
layout: post
slug: bashrc-not-executed
status: publish
title: .bashrc not executed
wordpress_id: '143'
categories:
- Linux
tags:
- bash
- Linux
- shell
---

Me and my friend Antonello, are going to start an experimental testing server to improve our skills in Ruby, PHP and start with Python as well.
After the installation, Antonello provided me an access created with webmin but, after the login I noticed that bashrc, actually bash, was not executed!
Editing /etc/passwd file, I was able to re-enable bash at login instead of sh:
your user line should look like
```
loginname:x:1001:1001::/home/antonio:/bin/bash
```
and not
```
loginname:x:1001:1001::/home/antonio:/bin/sh
```

;)

---
date: '2011-06-11 14:32:48'
layout: post
slug: nokogiri-rvm-homebrew-and-headhache
status: publish
title: Nokogiri, RVM, Homebrew and headhache!!!
wordpress_id: '391'
categories:
- mac
- Ruby
comments: true
---

Thanks to a gist (which I forked and slightly changed) I was able to finally install Nokogiri on my mac:

{% gist 1020543 %}

If you had MacPorts previously installed, it might still not work so
```
sudo mv /opt/local /opt/local_old
```
and try again.

Enjoy :)





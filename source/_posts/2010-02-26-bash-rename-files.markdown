---
comments: true
date: '2010-02-26 11:46:38'
layout: post
slug: bash-rename-files
status: publish
title: 'BASH: rename files'
wordpress_id: '329'
categories:
- shell
tags:
- awk
- bash
- rename
- xargs
---

A simple rename example using again the mighty awk and xargs  
```
ls -l *.xml | awk '{print $9}' | xargs -t -i mv {} {}.old
```
  
  
Explanation:  
**
```
ls -l *.xml
```
** -> easy! list the xml files in a folder  
**
```
awk '{print $9}'
```
** -> output just the name of the file  
**
```
xargs -t -i mv {} {}.old
```
** -> rename it adding at the same filename the extension ".old"  
  
I know, I know ... my explanation is crap: blame my laziness :)

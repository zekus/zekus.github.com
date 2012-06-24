---
date: '2008-06-11 17:20:30'
layout: post
slug: quick-solution-to-svn-checksum-mismatch-2
status: publish
title: 'quick solution to "svn: Checksum mismatch ..."'
wordpress_id: '106'
categories:
- Development
- Linux
- SVN
tags:
- checksum mismatch
- commit
- Development
- Linux
- SVN
---

If this error afflict your quiet development day, I'm sorry :D
I had this problem today and I solved in few steps:


  1. make a backup of the working copy in a different directory
  2. delete only the corrupted directory from your working copy
  3. make an svn update
  4. copy back only the modified files you need from the backup copy to the current working copy
  5. commit your changes
Now breath deeply and take a cold shower: I suppose you must be sweat! :D

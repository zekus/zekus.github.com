---
date: '2008-09-29 19:38:51'
layout: post
slug: svn-entry-has-unexpectedly-changed-special-status
status: publish
title: 'svn: Entry has unexpectedly changed special status'
wordpress_id: '127'
categories:
- SVN
tags:
- SVN
---

If you have this error after tryin a commit, for sure you have replaced a standard file with a symlink or viceversa, haven't you?

In that case, what you have to do is just **svn add <the resource changed>** and svn will replace the file with the new one!

Were you already scared :D ?

Anyway, the correct procedure to replace a real file with a symlink in svn is the following:



	
  1. **svn remove** of the file you want to link

	
  2. **ln -s <link>**

	
  3. **svn add** of the new link


;)

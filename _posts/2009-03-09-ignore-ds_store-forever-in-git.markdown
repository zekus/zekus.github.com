---
comments: true
date: '2009-03-09 02:26:25'
layout: post
slug: ignore-ds_store-forever-in-git
status: publish
title: ignore .DS_Store forever in GIT
wordpress_id: '171'
categories:
- GIT
- shell
tags:
- GIT
- scm
- version control
---

With a couple of little commands, you'll be able to ignore the .DS_Store files forever from your git repositories on mac!

The following command will add the .gitignore file to the git configuration
```
git config --global core.excludesfile ~/.gitignore
```

then, the following, will add the .DS_Store to the list

```
echo .DS_Store >> ~/.gitignore
```

and voilà!




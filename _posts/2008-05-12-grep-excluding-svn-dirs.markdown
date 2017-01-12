---
comments: true
date: '2008-05-12 13:33:16'
layout: post
slug: grep-excluding-svn-dirs
status: publish
title: grep excluding .svn dirs
wordpress_id: '101'
categories:
- Altro
- Development
- Linux
- mac
tags:
- grep
- shell
- SVN
---

Grep is a fantastic search command that let you filter results and give you what you need. It is used to search in the content of files and is very useful for programmers like us :)

Typically, when you search in a directory recursively and you want to exclude hidden directory such as the .svn, you so this:
```
grep -ri "your password is" * | grep -v .
```
this waste time cause search in all directories including the ones you want to exclude and then remove the unwanted results.
This other method, is the correct and quickest one:
```
grep -r 'content_graphic' assets/js --exclude=*\.svn*
```
**COOOL!**

If you want to make this permanent when you use grep, just put it in your profile file: on a Mac open ~/.profile with a text editor. If you're using Linux, edit ~/.bashrc or ~/.bash_profile or ~/.profile.

Add the following line to the top of the file:
```
export GREP_OPTIONS="--exclude=*\.svn*"
```
save and close!

Happy grepping to everybody ;)

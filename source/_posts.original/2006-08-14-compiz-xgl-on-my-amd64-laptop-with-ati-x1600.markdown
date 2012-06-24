---
date: '2006-08-14 14:24:00'
layout: post
slug: compiz-xgl-on-my-amd64-laptop-with-ati-x1600
status: publish
title: Compiz / Xgl on my Amd64 laptop with Ati x1600
wordpress_id: '13'
categories:
- Linux
---

Well, installing Xgl and Compiz has not been easy: there are a lot of valid tutorials out there,but somethimes they doesnt work for your system and this happened to me!  
I'll trace here, and link, the tutorials and modification I made to make things happen to my Ubuntu too and experiment with Xgl.  
  
First tutorial on the [Ubuntu Wiki](https://help.ubuntu.com/community/CompositeManager/Xgl) about Xgl. If you have some troubles on packets missing then use these repositories in your sources.list:  


> deb http://ubuntu.compiz.net/ dapper main  
deb http://xgl.compiz.info/ dapper main  
deb http://more.zubrowka.org/~julbouln/compiz/ ./  
deb-src http://xgl.compiz.info/ dapper main  
deb http://ubuntu.systemadministrator.org dapper eyecandy  
deb-src http://ubuntu.systemadministrator.org dapper eyecandy

Second on [Ubuntu Wiki](https://help.ubuntu.com/community/CompositeManager/InstallingCompiz) about installing Compiz.  
  
If you get some strange errors with compiz and the windows decorations don't appear, then you need to apply a patch to the code and reinstall patched debs:  


  1. download this [patch](http://www.compiz.net/attachment.php?item=548)  

  2. sudo apt-get build-dep compiz
  3. sudo apt-get source compiz
  4. cd into the unpacked dir
  5. sudo patch -p1 <>
  6. cd ..
  7. sudo apt-get source -b compiz
  8. sudo dpkg -i compiz*.deb
Here it is another [tutorial](http://www.ubuntuforums.org/showthread.php?p=739758) on ubuntuforums.org  
  
If you followed right all the steps described in the tutorials I suggested, you will see the magic of Xgl in front of your eyes ;)  
If you need more help, please visit www.compiz.net  
  
Happy Dapper  
Antonio

---
layout: post
title: "nokogiri again, but not its fault this time"
date: 2013-06-24 19:38
comments: true
categories: 
- ruby
- rails
- nokogiri
- libxml2
---

Today it was a total waste of time as I was trying to figure out why the F\* nokogiri was not getting installed into my new project gemset. 
First thing I had to figure out, was that Nokogiri now ships with libxml2 and libxslt that get compiled and installed with the gem itself.
Second thing was that libxslt was not getting compiled because it could not find an "acceptable grep"! Go figure! After many trials and unfruitful google
searches I decided to try with a different user and that maybe, if google was not returning any useful result, it was my configuration that was weird.
It turned out that I was correct and the problem was related to my *GREP_OPTIONS*. I had the following in my .zshrc
```bash
export GREP_OPTIONS="--exclude-dir=.svn --exclude-dir=.git -nR --color"
```
and, after removing the *-nR* options, I was finally able to install nokogiri correctly.


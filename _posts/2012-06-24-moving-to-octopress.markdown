---
layout: post
title: "moving to Octopress"
date: 2012-06-24 23:43
comments: true
categories:
---

I've been delaying this migrations for ages now but here we are, it finally happened:
I can write a blog post with my favourite editor now (Vim) and publish it to the web like a pro on my favourite dev website (GitHub) using git... that's too many emotions for one single day :P

### So, how did I do it? ###
There are tons of tutorials already on the net that explain very well how to migrate from Wordpress to Octopress so I'm not going to explain here all the details but make just a quick summary even for myself as a note:

- Download, install and follow the instructions of [exitwp](https://github.com/thomasf/exitwp)
- Run a regex to fix the code blocks like:
``` bash
perl -pi -e 's/([^\`]|^)(\`)([^\`]|$)/$1\n\`\`\`\n$3/g' *
```
- If you have been using Disqus on Wordpress before moving to Octopress, for some reason *exitwp* doesn't add the *comments: true* parameter in the posts so use this sed command to fix it:
``` bash
find _posts/ -type f -print0 | xargs -0 -I file sed -i '' '2 i\
comments: true
' file
```
- Octopress posts url is different from the Wordpress one so you're going to have to remap the Disqus comments using their [migration tool](http://help.disqus.com/customer/portal/articles/286778-using-the-migration-tools) and a bit of patience

The next step will be playing with the theme to make it more "personal" :)

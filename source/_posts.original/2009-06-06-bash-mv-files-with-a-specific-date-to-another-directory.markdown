---
date: '2009-06-06 16:43:33'
layout: post
slug: bash-mv-files-with-a-specific-date-to-another-directory
status: publish
title: 'bash: mv files with a specific date to another directory'
wordpress_id: '208'
categories:
- Linux
- shell
---

I was searching for a bash command to move files and directories from a folder to another with modified in a specific date for ages on google until I gave up and decided to write it myself:
```
 ls -l | awk '$6 == "2009-06-04" { print $8 }' | xargs -t -i mv {} /destination/folder
```
To understand what this line does, you need to know a bit about [awk](http://www.gnu.org/software/gawk/manual/gawk.html) and xargs (try "man xargs" in your shell)

Explaination:

ls -l : directory listing
awk '$6 == "2009-06-04" { print $8 } : take the files and dir with date 2009-06-04 and print the list
xargs -t -i mv {} /destination/folder : execute the mv command. {} is the result from the previous command.

I would like to explain you more, but I'm quite lazy and I leave you with google to undestand better the commands I've used.

Have fun! ;)

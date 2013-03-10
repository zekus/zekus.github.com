---
layout: page
title: "Vim Tricks Collection"
date: 2013-03-10 13:44
comments: true
sharing: true
footer: true
---

After years being a vim user, this is the place where I'm going to share my most used key bindings, plugins, shortcuts and cofigurations that I picheck up in Vim. 
Remember, with vim you will never end learing!

### copy and paste or move like a pro in the same document

``` vim
: m,n co k
```
it literally translates into: from line _m_ to line _n_, copy starting from line _k_
the same works with the command move:

``` vim
: m,n mo k
```

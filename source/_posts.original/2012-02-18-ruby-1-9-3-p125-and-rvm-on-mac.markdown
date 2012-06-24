---
date: '2012-02-18 15:32:41'
layout: post
slug: ruby-1-9-3-p125-and-rvm-on-mac
status: publish
title: Ruby 1.9.3-p125 and RVM on Mac
wordpress_id: '404'
categories:
- mac
- Ruby
---

A [new ruby version](http://www.ruby-lang.org/en/news/2012/02/16/ruby-1-9-3-p125-is-released/) is out and it's time to upgrade! The first try gave me this error:

```
?  ~  rvm install 1.9.3-p125
Error running ' ./configure --prefix=/Users/antonio/.rvm/rubies/ruby-1.9.3-p125 --enable-shared --disable-install-doc --with-libyaml --with-opt-dir=/Users/antonio/.rvm/usr ', please read /Users/antonio/.rvm/log/ruby-1.9.3-p125/configure.log
There has been an error while running configure. Halting the installation.
```

Adding the compiler option "--with-gcc=clang" worked:

```
?  ~  rvm install 1.9.3-p125 --with-gcc=clang
Install of ruby-1.9.3-p125 - #complete
```

enjoy Ruby :)

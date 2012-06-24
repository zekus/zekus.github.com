---
date: '2009-03-22 16:00:44'
layout: post
slug: rails-and-passenger-aka-mod_rails
status: publish
title: Rails and Passenger ( aka mod_rails )
wordpress_id: '182'
categories:
- Rails
- Ruby
tags:
- Apache
- composite primary keys
- gem
- mod_rails
- passenger
- Rails
- Ruby
---

We tried to setup a rails application in a server subfolder in a way that could have been accessible through an URL like http://servername/rails,  so we followed the configuration manual for mod_rails.We found that, to make rails works in a subfolder, should have used the Apache parameter RailsBaseURI.

With a great surprise, that didn't worked so we started trying all possible apache configuration combinations to avoid that 404 error that was becoming a nightmare.

After few hours we started doubting about our Apache knowledge and even about our capacity of reading and following a couple of stupid instructions on a website!

We gave up and we started googling around when... the solution came out from dozens of blogs, forums and newsletters:


> MOD_RAILS IS NOT COMPATIBLE WITH RAILS 2.2.2 AND ITS NEW ROUTING SYSTEM


"HOLY CRAP" was our esclamation and I will not mention here all the italian's bad words that suddenly came out from our mounth!

So, here the solution: put this line here
```
config.action_controller.relative_url_root = "/guestbook"
```
in your environment.rb

Now restart apache and enjoy!

ps. why hadn't we changed mod_rails with mongrel or anything different? I don't know!!!!


![](http://img.zemanta.com/pixy.gif?x-id=737895d3-2f2e-43e4-8cec-477c62acba02)

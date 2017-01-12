---
comments: true
date: '2010-06-21 23:17:54'
layout: post
slug: rails-and-postgresql
status: publish
title: Rails and PostgreSQL
wordpress_id: '357'
categories:
- Rails
tags:
- postgres
- postgresql
- Rails
- Ruby
---

Complaining, screaming, sweating, swearing .... why it doesnt work ... jeeeeeezzz
```
/opt/local/lib/ruby/gems/1.8/gems/activerecord-2.3.8/lib/active_record/connection_adapters/abstract/connection_specification.rb:76:in 
```
establish_connection': Please install the postgres adapter: 
```
gem install activerecord-postgres-adapter
```
 (no such file to load -- active_record/connection_adapters/postgres_adapter) (RuntimeError)
```
  
  
And then a light ... "I upgraded postgresql recently!"  
  
Just reinstall the postgres gem and you are done...  
  
What a night!

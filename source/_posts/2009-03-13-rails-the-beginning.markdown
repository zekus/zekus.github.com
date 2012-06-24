---
comments: true
date: '2009-03-13 23:45:05'
layout: post
slug: rails-the-beginning
status: publish
title: Rails ... the beginning
wordpress_id: '173'
categories:
- Rails
- Ruby
tags:
- migrate
- Rails
- Ruby
- scaffold
---

Finally I started a little RoR project with my friend Antonello but we did it in the wrong way :D  
  
We started from the database design (not exactly the rails way) and we are trying to solve problems that a Rails developer usually doesn't have like create the scaffold without migration scripts!  
  
Here are 3 simple steps to do it:  
	

  * rake db:schema:dump (create the schema dump from the existing database)
	
  * mv db/schema.rb db/migrate/001_initial.rb (create the initial migration script manually)  

	
  * script/generate scaffold firstmodule field1:text field2:varchar field3:date --skip-migration
The most important thing you should never forget is that your tables on the database must have a PLURAL name but use the SINGULAR name when you create the scaffold for that table.  
( ex: the table name is "tools" but the command to create the scaffold is script/generate scaffold tool )  
  
Happy RoRing !!!  
  


![](http://img.zemanta.com/pixy.gif?x-id=6ccfe230-6968-422e-b5c5-6c6f3bfe43ec)

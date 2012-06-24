---
date: '2008-02-13 21:48:37'
layout: post
slug: getting-crazy-with-mysql-and-macport
status: publish
title: getting crazy with mysql and MacPort
wordpress_id: '90'
categories:
- mac
- mysql
---

Have you ever had an error like this???
```
macbook-di-antonio-lorusso:var zekus$ sudo /opt/local/share/mysql5/mysql/mysql.server start
Starting MySQL
.../opt/local/share/mysql5/mysql/mysql.server: line 159: kill: (22793) - No such process
ERROR!
```
Please check permissions because you have a problem with that!
Check that the owner of **/opt/local/var/db**  and  **/opt/local/var/run/mysql5** is  **_mysql** group **admin**.

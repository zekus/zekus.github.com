---
comments: true
date: '2009-08-14 01:11:10'
layout: post
slug: macports-php-5-3-and-mysqlnd
status: publish
title: MacPorts, PHP 5.3 and Mysqlnd
wordpress_id: '230'
categories:
- Altro
---

If you have recently upgraded to php 5.3 and you have done it using
```
sudo port install php5 +apache2+macosx+mysqlnd+pear
```

you should have noticed that you cannot use mysql anymore because of an error that, I'm sure, is driving you crazy
```
PHP Warning: mysqli::mysqli(): [2002] No such file or directory (trying to connect via unix:///tmp/mysql.sock) in /Users/antonio/Sites/db.php on line 25

PHP Warning: mysqli::mysqli(): (HY000/2002): No such file or directory in /Users/antonio/Sites/db.php on line 25
```
The problem comes from php and unfortunately is only fixable changing the location of the mysql.sock from the usual macports directory /opt/local/var/run/mysql5/mysqld.sock to /tmp/mysql.sock editing the file /opt/local/etc/my.cnf

;)





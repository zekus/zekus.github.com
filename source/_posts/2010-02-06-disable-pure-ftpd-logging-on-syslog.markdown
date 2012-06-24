---
comments: true
date: '2010-02-06 14:33:04'
layout: post
slug: disable-pure-ftpd-logging-on-syslog
status: publish
title: disable Pure-ftpd logging on syslog
wordpress_id: '322'
categories:
- Linux
- shell
tags:
- Linux
- log
- pure-ftpd
- ubuntu
---

Pure-ftpd is a bit tricky to configure because do not handle the configuration like any other daemon in Linux so you will not find any /etc/pure-ftpd.conf.

According to the pure-ftpd documentation, you should start the daemon already with the options you need. The default Ubuntu installation, use the files in /etc/pure-ftpd/conf/ to set the options for the startup script of pure-ftpd so, to disable the logging, execute the following command in your shell and restart the daemon
```
$ echo "none" > /etc/pure-ftpd/conf/SyslogFacility
$ /etc/init.d/pure-ftpd-mysql restart
```

;)

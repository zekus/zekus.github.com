---
date: '2005-11-17 17:36:00'
layout: post
slug: the-cron-jobs
status: publish
title: the Cron Jobs :)
wordpress_id: '59'
categories:
- Linux
---

_(* extract from suse administration manual )_
  
The cron tables are located in /var/spool/cron/tabs. /etc/crontab  serves as a systemwide cron table. Enter the name of the user who should run the command directly after the time table. In Example 10.1, “Example of an Entry in /etc/crontab”, root is entered. Package-specific tables, located in /etc/cron.d, have the same format. See man cron.
  

  
Example 10.1. Example of an Entry in /etc/crontab
  

  
1-59/5 * * * * root test -x /usr/sbin/atrun && /usr/sbin/atrun
  

  
/etc/crontab cannot be processed with crontab -e. It must be loaded directly into an editor, modified, then saved.
  

  
A number of packages install shell scripts to the directories /etc/cron.hourly, /etc/cron.daily, /etc/cron.weekly, and /etc/cron.monthly, whose instructions are controlled by /usr/lib/cron/run-crons. /usr/lib/cron/run-crons is run every 15 minutes from the main table (/etc/crontab). This guarantees that processes that may have been neglected can be run at the proper time.
  

  
The daily system maintenance jobs have been distributed to various scripts for reasons of clarity. They are contained in the package aaa_base. /etc/cron.daily contains, for instance, the components backup-rpmdb, clean-tmp, or clean-vi. 

[![](http://www.feedburner.com/fb/images/pub/flchklt.gif)](http://feeds.feedburner.com/zekussuse)

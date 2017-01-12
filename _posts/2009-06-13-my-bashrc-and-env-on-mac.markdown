---
comments: true
date: '2009-06-13 13:29:16'
layout: post
slug: my-bashrc-and-env-on-mac
status: publish
title: my .bashrc and env on mac
wordpress_id: '212'
categories:
- Altro
---

If someone find it useful... I do and this post is, honestly, for my record:

```
bash-3.2$ env
APSX2=/opt/local/apache2/bin/apxs
MANPATH=/opt/local/share/man:/opt/local/share/man:/opt/local/share/man:/opt/local/share/man:/usr/share/man:/usr/local/share/man:/usr/X11/man
TERM_PROGRAM=iTerm.app
LC_MONETARY=en_GB.UTF-8
SHELL=/bin/bash
TERM=xterm
LC_NUMERIC=en_GB.UTF-8
COMMAND_MODE=legacy
__CF_USER_TEXT_ENCODING=0x1F5:0:0
PATH=/opt/local/apache2/bin:/opt/local/bin:/opt/local/sbin:/opt/local/apache2/bin:/opt/local/bin:/opt/local/sbin:/opt/local/apache2/bin:/opt/local/bin:/opt/local/sbin:/opt/local/apache2/bin:/opt/local/bin:/opt/local/sbin:/opt/local/apache2/bin:/opt/local/bin:/opt/local/sbin:/opt/local/bin:/opt/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin:/usr/X11/bin
LC_MESSAGES=en_GB.UTF-8
LC_COLLATE=en_GB.UTF-8
PWD=/Users/zekus
EDITOR=/usr/bin/mate -w
LANG=en_GB.UTF-8
HOME=/Users/zekus
SHLVL=1
LOGNAME=zekus
LC_CTYPE=en_GB.UTF-8
DISPLAY=:0.0
SECURITYSESSIONID=613f90
LC_TIME=en_GB.UTF-8
_=/usr/bin/env
```

```
bash-3.2$ cat ~/.bashrc
export PATH=/opt/local/apache2/bin:/opt/local/bin:/opt/local/sbin:$PATH
export MANPATH=/opt/local/share/man:$MANPATH
export DISPLAY=:0.0
export EDITOR='/usr/bin/mate -w'
export APSX2='/opt/local/apache2/bin/apxs'
alias mysqld='sudo /opt/local/share/mysql5/mysql/mysql.server'
alias apachectl='sudo /opt/local/apache2/bin/apachectl'
alias mysql='mysql5'
alias rake='/opt/local/bin/rake'
alias rails='/opt/local/bin/rails'
alias ruby='/opt/local/bin/ruby'
postgresqlctl () { sudo su postgres -c "/opt/local/lib/postgresql83/bin/pg_ctl $1 -D /opt/local/var/db/postgresql83/defaultdb"; }
```

Note the last row in the bashrc: is a function to load the postgres server on demand!

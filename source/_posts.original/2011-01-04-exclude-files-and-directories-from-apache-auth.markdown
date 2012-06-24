---
date: '2011-01-04 11:35:52'
layout: post
slug: exclude-files-and-directories-from-apache-auth
status: publish
title: Exclude files and directories from Apache Auth
wordpress_id: '378'
categories:
- Altro
tags:
- Apache
- authentication
- location
- locationmatch
- setenvif
---

It would have made sense to use LocationMatch with a negative lookahead regex pattern like "^/(?!admin)" but that doesnt work. Neither work a rule like !"^/admin" so here is a workaround:  
  
```
<Location "/">  
AuthType Basic  
AuthName "Restricted Files"  
AuthUserFile /var/www/clients/client12/web17/passwd  
AuthGroupFile /dev/null  
Require valid-user  
SetEnvIf Request_URI "^/(admin|skin|js|index)(.*)$" allow  
SetEnvIf Request_URI "^/favicon.ico$" allow  
Order allow,deny  
Allow from env=allow  
Satisfy Any  
</Location>
```
  
  
This basically allow the access without authentication to the directories/files that start with admin, skin, js or index. The other rule allow the favicon too.

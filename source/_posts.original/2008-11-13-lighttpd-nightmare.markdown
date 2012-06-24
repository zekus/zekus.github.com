---
date: '2008-11-13 14:38:56'
layout: post
slug: lighttpd-nightmare
status: publish
title: LightTPD nightmare
wordpress_id: '145'
categories:
- Altro
- Development
- Linux
tags:
- 2tls
- domain
- lighttpd
- regex
- subdomain
- tld
---

if are trying to use mod_evhost in lighttpd in a more advanced way like using deep subdomains or with particulars tld like "co.uk" aka 2tls, you should know that
```
$HTTP["host"] =~ "^([^.]+)\.([^.]+)\.babelclient\.photobox\.([^.]+)\.([^.]+)$"{
evhost.path-pattern = "/web/%5/%6/assets"
}
```
will NEVER WORK but
```
$HTTP["host"] =~ "^([^.]+)\.([^.]+)\.babelclient\.photobox\.([^.]+)\.([^.]+)"{
evhost.path-pattern = "/web/%5/%6/assets/"
}
```
WILL WORK.

compare the two pieces of code and start screaming like a mad!

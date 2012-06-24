---
date: '2012-05-23 16:57:38'
layout: post
slug: mod_rpaf-and-ubuntu-12-04
status: publish
title: mod_rpaf and ubuntu 12.04
wordpress_id: '419'
categories:
- Altro
---

<rant> Canonical, seriously, what's wrong with you people? How dare you calling the 12.04 a LTS version? Have you testend on EC2? and cloud-init? It's a bloody mess! </rant>

So, you upgraded and mod_rpaf behind your proxy is not working anymore? Do this:

FROM =====>
```
<IfModule mod_rpaf.c>
RPAFenable On
RPAFsethostname On
RPAFproxy_ips 127.0.0.1
</IfModule>
```

TO =======>
```
<IfModule mod_rpaf-2.0.c>
RPAFenable On
RPAFsethostname On
RPAFproxy_ips 127.0.0.1
</IfModule>
```

Find the differences and thank [this guy](http://ffnz.tumblr.com/post/23078644987/rpaf-mod-not-working-on-ubuntu-12-04) that find it before me.

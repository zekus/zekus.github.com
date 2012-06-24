---
date: '2007-07-06 14:45:58'
layout: post
slug: vmware-server-on-ubuntu-pt2
status: publish
title: vmware server on ubuntu (pt.2)
wordpress_id: '70'
categories:
- Linux
---

Damn! All went almost well installing vmware-server but  I'm still getting crazy on iptables.
I'm playing with [Firewall Builder](http://www.fwbuilder.org) that, at moment, seems more complicated than iptables itself!

Anyway... I'll link a pair of reference used to install vmware-server on ubuntu Feisty and vmware-server-mui (the web interface of vmware):[](https://help.ubuntu.com/community/VMware/Server?action=show&redirect=VmwareServer)

[The Ubuntu Wiki Way](https://help.ubuntu.com/community/VMware/Server?action=show&redirect=VmwareServer)
[Antonio Doldo Blog](http://adoldo.wordpress.com/2007/03/06/vmware-server-installazione-su-ubuntu-feisty-herd-5/)
[http://users.piuha.net/martti/comp/ubuntu/server.html](http://users.piuha.net/martti/comp/ubuntu/server.html)

The summary of this three sites is:

Register for free to [http://register.vmware.com/content/registration.html](http://register.vmware.com/content/registration.html) and get your serials

Add the commercial repo from Canonical
```
deb http://archive.canonical.com/ubuntu feisty-commercial main
```
in your /etc/apt/sources.list and update your sources
```
sudo apt-get update
```
Install the vmware-server package
```
sudo apt-get install vmware-server
```
Apply the following patch to /etc/pam.d/vmware-authd to make permissions work well:
```
#%PAM-1.0
auth required pam_unix_auth.so shadow null
ok
account required pam_unix_acct.so
```
get the Management Interface pack
```
wget http://download3.vmware.com/software/vmserver/VMware-mui-1.0.2-39867.tar.gz
```
unpack it and install
```
tar zxvf VMware-mui-1.0.2-39867.tar.gz
cd vmware-mui-distrib/
sudo ./vmware-install.pl
```
fix mui boot script
```
cd /tmp
wget http://users.piuha.net/martti/comp/ubuntu/httpd.vmware.diff
cd /
patch -b -p0 < /tmp/httpd.vmware.diff
```
Now, your vmware server is installed and runnig and you can access to your management interface from firefox at **https://localhost:8333** or via the Management Console at "_Applications -> Administration Tools -> VMWare Server Console_".

Wait for Pt.3 of this adventure where I'll talk about networking and VMWare ( ... if I'll survive ... )!

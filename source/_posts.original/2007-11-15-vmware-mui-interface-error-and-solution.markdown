---
date: '2007-11-15 10:49:11'
layout: post
slug: vmware-mui-interface-error-and-solution
status: publish
title: vmware mui interface error and solution
wordpress_id: '80'
categories:
- Linux
- vmware
---

After a server reboot, I've had some problem accessing the mui interface on https://localhost:8333. The server vmware.httpd didnt want to start so I checked the /var/log/vmware-mui/error_log and I found the following error:
```
[Thu Nov 15 08:37:46 2007] [error] ModVmdb load: Address of ModVmdb_InitCore: 0xb7c745a0\n
[Thu Nov 15 08:37:46 2007] [error] Failed to create named-pipe directory:
/var/run/vmware//httpd/8234: No such file or directory\n
[``Thu Nov 15 `` 08:37:46 2007] [error] VMWARE PANIC: \nNOT_IMPLEMENTED F(4023):707\n
[``Thu Nov 15 `` 08:37:46 2007] [error] Panic: Could not allocate temporary context.\n
```

The solution was a stupid permission change:
```
# sudo mkdir /var/run/vmware/httpd
# sudo chown www-data /var/run/vmware/httpd
# sudo chmod 700 /var/run/vmware/httpd
```

After that, I started the mui interface and all went fine again:
```
# sudo /etc/init.d/httpd.vmware start
```

Anyway, I noticed that it happens with every reboot so I added the following code directly in /etc/init.d/httpd.vmware to the start of the function vmware_start_httpd():
```
HTTPD_RUN_DIR="/var/run/vmware/httpd"
[ -d "$HTTPD_RUN_DIR" ] || mkdir $HTTPD_RUN_DIR
chmod 777 $HTTPD_RUN_DIR
```

Now all seems running well!

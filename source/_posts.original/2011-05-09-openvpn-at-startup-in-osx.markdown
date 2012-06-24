---
date: '2011-05-09 00:11:25'
layout: post
slug: openvpn-at-startup-in-osx
status: publish
title: OpenVPN at startup in OSX
wordpress_id: '386'
categories:
- mac
tags:
- mac
- openvpn
- osx
- tunnelblick
- vpn
---

The easiest way of getting an OpenVPN client on mac is with [Tunnelblick](http://code.google.com/p/tunnelblick/wiki/DownloadsEntry?tm=2) but you will join the VPN only when you have logged in. Sometimes you need your mac to connect at startup instead and I'll show you how to do it:

create /etc/rc.local and copy/paste the following three lines in it:

```
#!/bin/bash
/sbin/kextload /Applications/Tunnelblick.app/Contents/Resources/tap.kext
/sbin/kextload /Applications/Tunnelblick.app/Contents/Resources/tun.kext
```

then create a Launch script like this for each of the vpn you want to connect to, replacing _YOURVPNNAME_, _YOURCONFIGFILE_, _YOUR/CONFIG/FOLDER_ accordingly:

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
<key>Label</key>
<string>org.openvpn.YOURVPNNAME</string>
<key>OnDemand</key>
<false/>
<key>Program</key>
<string>/Applications/Tunnelblick.app/Contents/Resources/openvpn</string>
<key>ProgramArguments</key>
<array>
<string>openvpn</string>
<string>--config</string>
<string>YOURCONFIGFILE.conf</string>
</array>
<key>RunAtLoad</key>
<true/>
<key>TimeOut</key>
<integer>90</integer>
<key>WorkingDirectory</key>
<string>YOUR/CONFIG/FOLDER</string>
</dict>
</plist>
```

save each script into _/Library/LaunchDaemons/_ folder using a name for the file like _org.openvpn.YOURVPNNAME.plist_, then change the user and group to root:wheel with the following command in a terminal window:

```
sudo chown root:wheel /Library/LaunchDaemon/org.openvpn.YOURVPNNAME
```

last commands to register and execute your Launch scripts are:

```
sudo launchctl load /Library/LaunchDaemon/org.openvpn.YOURVPNNAME.plist
sudo launchctl start org.openvpn.YOURVPNNAME
```

a restart should be the very last thing to do and once your mac has started you shoud be connected to your vpn network(s)!

enjoy ;)

**UPDATE: **the new version of tunnelblick 3.2beta26 does have the the "connect when computer starts" functionality that automatically makes this post obsolete. I'll just keep it for the records :)

---
comments: true
date: '2006-03-07 01:18:00'
layout: post
slug: speedy-boot
status: publish
title: Speedy boot
wordpress_id: '8'
categories:
- Linux
---

Here is a list of things that maybe you dont need or dont want they load at boot time:  
  
sudo update-rc.d -f mdadm remove    <-- this and next for Raid  
sudo update-rc.d -f mdadm-raid remove  
sudo update-rc.d -f lvm remove   <-- multi partition volumes(big arrays)  
sudo update-rc.d -f evms remove            <-- multi disk management  
sudo update-rc.d -f powernowd remove  <-- CPU frequency scaling  
sudo update-rc.d -f ntpdate remove  <-- keep clock sync to ubuntu  
sudo update-rc.d -f cupsys remove  <-- I "scp" files to my main desktop  
sudo update-rc.d -f hplip remove  <--HP Linux Inkjet Printing  
sudo update-rc.d -f acpid remove    <-- BIOS is not acpi aware  
sudo update-rc.d -f acpi-support remove <-- don't care about power saving  
  
have an happy quick Ubuntu :)  
Antonio

---
comments: true
date: '2006-03-05 22:07:00'
layout: post
slug: apache2-virtual-hosts
status: publish
title: Apache2 Virtual Hosts
wordpress_id: '6'
categories:
- Linux
---

Hey guys,  
we're going to add a new virtual host in apache2  
  
1) create a new virtual host file in /etc/apache2/sites-available  


 

Code:

 
    
    <div style="text-align: left;" dir="ltr">$ cd /etc/apache2/sites-available<br></br>$ touch newhost</div>

2) use your favourite editor to put what follows in that file. Change the document root to wherever you want to put your host. Change the server name to the address where you want to access your host:  


 

Code:
    
    <br></br><VirtualHost *><br></br>   ServerName rails<br></br>   DocumentRoot /var/www/newhost/<br></br><br></br>   <Directory /var/www/newhost/><br></br><br></br>       AllowOverride all<br></br>       Order allow,deny<br></br>       Allow from all<br></br><br></br>   </Directory><br></br></VirtualHost>

3) having set up this file, we then need to symlink to it from the sites-enabled directory. Let's do that now:  
  


 

Code:

 
    
    <div style="text-align: left;" dir="ltr">$ cd /etc/apache2/sites-enabled<br></br>$ ln -s ../sites-available/newhost newhost</div>

  
4) In order to get the apache2 server to display this site when you access it, you've got to add this ServerName alias next to 127.0.0.1 in your /etc/hosts file, or your web browser is _not_ going to know where to go when you give it in your address bar. Here's the beginning of mine:  
  


 

Code:

 
    
    <div style="text-align: left;" dir="ltr">127.0.0.1 newhost etc...</div>

  
5) Now we're pretty well done (so long as I haven't left a step out). Restart your apache2 with:  
  


 

Code:

 
    
    <div style="text-align: left;" dir="ltr">$ /etc/init.d/apache2 restart</div>

  
  
see you next,  
Antonio  
  
ps. Thanks to [Siennalizard](http://ubuntuforums.org/showthread.php?p=748531)

---
layout: post
title: "SSH as a proxy server in Windows"
description: ""
category: 
tags: [ec2, Amazon, ssh, windows, proxy]
---



First of all, we need a proper SSH client, here we use [PuTTY](http://en.wikipedia.org/wiki/PuTTY), you can download it [here](http://the.earth.li/~sgtatham/putty/latest/x86/putty.exe). 
And then you can follow the next steps to complete the configuration.
####Use PuTTY as SSH Client
#####Host name settings:
    Host: 54.251.58.63 
    Port: 50683
    Connection Type: SSH

![Host name and port setting](http://darlinglele.github.com/images/ssh/host.jpg)
#####Private key file settings:
    The private key protect your information secure bettween ssh client and server, even if connected to a insecure network.
![Host name and port setting](http://darlinglele.github.com/images/ssh/keyfile.jpg)
#####Forwarding port settings:
    Port: 3128 use this port to forward the requests to ssh server.

######Don't forget to add this port by click 'Add' button


![Host name and port setting](http://darlinglele.github.com/images/ssh/forwarding.jpg)
#####Proxy settings
    This is an option if you are using proxy to connect internet.
![Host name and port setting](http://darlinglele.github.com/images/ssh/proxy.jpg)

    Then you can save the configuration and click open button to connect server. 
######Enter the ssh user
    Login as : ubuntu 
####Use SwitchySharp to sharp the chrome


Since we already successful setting up the forward port in 3128, then we are going to config chrome to use this port as socket proxy, here we can get many convienent by install an amazing chrome extesion -- SwitchyProxy, you can easily to install by hit [me](https://chrome.google.com/webstore/detail/dpplabbmogkhghncfbfdeeokoefdjegm)

#####Config the proxy profiles
    Socks host: localhost 
    Port: 3128 
    notes: The locahost 3128 port will be the tunnel that forwarding the requests from chrome browser.

![Host name and port setting](http://darlinglele.github.com/images/ssh/profiles.png)

#####Config the switch rule
    The easiest way is using rule list url from https://autoproxy-gfwlist.googlecode.com/svn/trunk/gfwlist.txt 
    When the url you are requesting is in the list, the request will forward to port 3128 using ssh protocal.  
![Host name and port setting](http://darlinglele.github.com/images/ssh/rule.png)


######The end.
{% include JB/setup %}

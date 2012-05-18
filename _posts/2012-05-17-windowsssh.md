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
    Host: ec2-54-251-1-36.ap-southeast-1.compute.amazonaws.com
    Port: 50683
    Connection Type: SSH

![Host name and port setting](http://darlinglele.github.com/images/ssh/host.jpg)
#####Private key file settings:
    The private key protect your information secure bettween ssh client and server, even if connected to a insecure network.
![Host name and port setting](http://darlinglele.github.com/images/ssh/keyfile.jpg)
#####Forwarding port settings:
    Port: 3128 use this port to forward the requests to ssh server.
![Host name and port setting](http://darlinglele.github.com/images/ssh/forwarding.jpg)
#####Proxy settings
    This is an option if you are using proxy to connect internet.
![Host name and port setting](http://darlinglele.github.com/images/ssh/proxy.jpg)

    Then you can save the configuration and click open button to connect server. 
####Use SwitchySharp to sharp the chrome


Since we have successful forward the ssh port with localhost 3128 port, then we are going to config chrome to use this port as socket proxy, here we can get many convienent by install an amazing chrome extesion -- SwitchyProxy, you can easily to install by hit [me](https://chrome.google.com/webstore/detail/dpplabbmogkhghncfbfdeeokoefdjegm)

#####Config the proxy profiles
    Socks host: localhost 
    Port: 3128 
    
![Host name and port setting](http://darlinglele.github.com/images/ssh/profiles.png)
#####Config the switch rule
    The easiest way is using rule list url from https://autoproxy-gfwlist.googlecode.com/svn/trunk/gfwlist.txt 
![Host name and port setting](http://darlinglele.github.com/images/ssh/rule.png)







{% include JB/setup %}

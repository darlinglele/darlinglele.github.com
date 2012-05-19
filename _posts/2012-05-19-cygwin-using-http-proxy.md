---
layout: post
title: "Using http proxy in cygwin"
description: ""
category: 
tags: [cygwin, http proxy]
---
As a windows user, I prefer to use cygwin for the benifit of powerful linux tools . Cygwin provides a collection of linux tools, and brings linux look and feel for windows.

In some organization secutity policy, they use http proxy to connect internet. For many applications(eg.IE), it's necessary to config the http proxy for internet accessable. 
For cygwin there are many tools need connect to internet, so the first thing for me is to config http proxy for cygwin. It's straightforward and easy, just one line:
    
    export http_proxy="http://username:password@proxyserver:port"
    or
    export http_proxy="http://proxyserver:port"
For write once run every times, it is a good idea to save the command into .bash_profile file.
{% include JB/setup %}

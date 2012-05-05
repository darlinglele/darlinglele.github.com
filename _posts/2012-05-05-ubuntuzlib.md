---
layout: post
title: "在ubuntu中安装zlib"
description: ""
category: Notes 
tags: [zlib,ubuntu,rvm]
---

在ubuntu 12.04中安装好rvm 和ruby，使用gem install rake 命令来安装rake，安装过程中发现 no such file to load --zlib 错误。

解决的方法是安装zlib后重新安装ruby。

安装zlib：
    
    rvm pkg install zlib

另外，无法通过apt-get install zlib来安装zlib包

重新安装ruby：

    rvm remove 1.9.3 
    rvm install 1.9.3
{% include JB/setup %}

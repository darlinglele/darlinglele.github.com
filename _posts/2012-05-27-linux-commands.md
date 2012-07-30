---
layout: post
title: "Linux commands"
description: "notes about linux commands"
category: 
tags: [chmod, rename, nohup, command, ls, sed, awk]
---
Here attached some commands had been used frequently:

    curl darlinglele.github.com|sed's/[^a-zA-Z]/ /g' | tr 'A-Z ' 'a-z\n'|grep '[a-z]'|sort -u
Get the words contained in a page

    rename '/y/A-Z/a-z/' * 
Rename all to lowercase

    fuser -n tcp 8080
Find the processes using 8080 port

    update-alternatives --config java
Configure java different versions 

    ls ./* -D 
Show all directory

    chmod 777 /var/chef/ -R
Grant full right of /var/chef and subfolder to any user.    

    nohub command &
    eg: nohub jekyll --server &
Run command in new precess 

    Ctrl+z 
    bg %PID
Stop and run current process backgroup, the process still hook to the terminal.

    sed [option] command files
    eg: sed -i "s/zhixiong/Jason/g"  `grep zhixiong -rl /c/sql/`
Replace all "zhixiong" with "Jason" in files return by grep command

    ls | awk '{printf("%s ",$1)}'
Valuable to print with format
{% include JB/setup %}

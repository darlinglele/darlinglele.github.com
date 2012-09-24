---
layout: post
title: "Git commands"
description: ""
category: 
tags: [git checkout reset revert]
---
{% include JB/setup %}
 
git是一个分布式的版本控制系统，最初是开发linux内核的版本控制工具。它和svn，cvs不同， 它采用分布式版本控制方式，不需要服务段的支持。

因此，git无论作为个人项目或者团队开发都是很重要的工具。git正常情况下使用命令来完成任务，因此 checkout掌握和熟悉一些常用的命令会让工作更加有效率。 

	git checkout <commit> -- filename 这个命令非常有用，它可以方便的签出任意版本下的任意文件到当前的工作区。如果你需要签出某个<commit>,你只需要
	git checkout <commit> 或者git reset <commit> 

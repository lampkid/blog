---
title: 'HOWTO:在Windows上根据IP查看主机名称'
id: 678
categories:
  - HOWTO
  - 网络
date: 2012-11-07 13:14:19
tags:
---

在Windows上，可以使用nbtstat命令查看网络上的主机名称：
如：
[bash]
nbtstat -A 192.168.56.1
[/bash]
当然，我们也可以使用nbtstat 根据指定名称获取对应的主机名称表：
[bash]
nbtstat -a LAMPKID-PC
[/bash]
nbtstat命令的具体使用方法参考nbtstat -h:

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/11/netstat.png "netstat")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/11/netstat.png)
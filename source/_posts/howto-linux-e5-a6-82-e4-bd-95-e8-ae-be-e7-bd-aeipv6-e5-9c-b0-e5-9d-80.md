---
title: 'HOWTO: Linux如何设置IPv6地址'
tags:
  - HOWTO
  - Linux
id: 642
categories:
  - HOWTO
  - Linux
date: 2012-10-10 10:04:39
---

[bash]
#为网口eth0添加ip地址：
sudo ifconfig eth0 add ip地址

#删除绑定在eth0上的ip地址：
sudo ifconfig eth0 del ip地址
[/bash] 
---
title: vim中用空格替换Tab
tags:
  - Vim
id: 972
categories:
  - HOWTO
  - Vim
date: 2014-07-08 13:20:18
---

在vim配置文件中添加如下配置：

[bash]
set ts=4  &quot;tabstop ，设置tab为4个空格&lt;/pre&gt;
set expandtab
[/bash]

如果原来文件中的tab占据8个空格，可以有两种处理方式：

1.打开vim使用%s/\t/        /g将所有\t替换为8个空格。

2.使用sed -i替换

参考：

http://blog.csdn.net/jiang1013nan/article/details/6298727
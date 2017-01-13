---
title: Python过滤列表中的空字符串
tags:
  - Python
  - 字符串处理
id: 792
categories:
  - HOWTO
  - Python
date: 2013-08-10 06:27:34
---

list = ['', ' ', '3', 'b', 'c', '   ']
1\. list = filter(lambda x: str(x).strip(), list)  
2\. list = [ x for x in list if not x.strip() ] 
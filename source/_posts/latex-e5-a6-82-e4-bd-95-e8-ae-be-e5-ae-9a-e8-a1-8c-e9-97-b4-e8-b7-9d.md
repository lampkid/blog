---
title: latex如何设定行间距
tags:
  - Tex
  - 行间距
id: 471
categories:
  - HOWTO
  - Tex
  - 工具
  - 文档创作
  - 毕业设计
date: 2012-03-22 12:43:43
---

&nbsp;

在documentclass后面(即在导言区)加入一行代码即可:

[tex]
\documentclass[aps,prl,reprint,twocolumn,groupedaddress]{revtex4-1}
\linespread{1.3}
[/tex]

\linespread{1.3}为一行半间距，1.6为两倍间距。
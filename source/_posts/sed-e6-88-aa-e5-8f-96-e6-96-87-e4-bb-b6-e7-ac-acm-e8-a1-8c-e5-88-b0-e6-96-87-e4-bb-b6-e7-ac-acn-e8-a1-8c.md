---
title: sed截取文件第m行到文件第n行
tags:
  - Bash
  - Linux
  - sed
id: 776
categories:
  - HOWTO
  - Linux
date: 2013-06-26 07:27:26
---

截取test.txt中第405行到415行，然后保存到文件save.txt:

sed '405,415p;415q' test.txt > save.txt

还可以使用vim截取：

:startlinenumber, endlinenumberw newfilename

或 

:startlinenumber, endlinenumberw>>newfilename

>>表示追加
 
---
title: '#Linux##Shell#命令行编辑'
tags:
  - Shell
id: 230
categories:
  - HOWTO
  - Linux
  - 工具
date: 2012-01-03 13:21:51
---

今天很意外，不小心在键盘上触动了两个键Ctrl + W , 奇迹出现了。Shell终端的命令没了。这意味着，Ctrl+W是清空Shell终端当前命令。

以前经常用的两个命令行编辑命令：

Ctrl+a: 跳回当前命令开始，即移至行首 ；

Ctrl+w:跳到当前命令结尾，即移至行尾；

于是上网继续了解：
> Ctrl+b            或左箭头键 左移一个字符（移至前一个字符）> 
> Ctrl+f            或右箭头键 右移一个字符（移至后一个字符）> 
> 
> Esc b             左移一个单词> 
> Esc f             右移一个单词  。> 
> Ctrl+d            删除光标所在处的字符  （Del）> 
> Ctrl+h 删除光标左边的字符 （BACKSPACE）> 
> Ctrl+k            删除至行尾
Esc f 命令有点问题，可能是我终端下快捷键映射的冲突吧，不了解。

参考：

[51CTO.com](http://os.51cto.com/art/200912/173300.htm)

更多：

[linuxsir](http://www.linuxsir.org/main/node/151)
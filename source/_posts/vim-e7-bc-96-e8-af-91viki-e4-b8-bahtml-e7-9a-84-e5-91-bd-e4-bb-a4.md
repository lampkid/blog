---
title: '#vim# 编译viki为HTML的命令'
id: 393
categories:
  - HOWTO
  - Vim
  - 文档创作
  - 编辑器
date: 2012-02-05 03:49:22
tags:
---

deplate  -m utf8 -m lang-zh_CN-autospace -m code-highlight -X -t bright.html --css bright  TheBasics.viki

将bright.html 拷贝到~/.deplate/templates/下，将bright.css拷贝到 ~/.deplate/css/下
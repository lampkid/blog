---
title: 音频格式转化：如何将wav转化为mp3
id: 757
categories:
  - HOWTO
  - 多媒体
  - 工具
date: 2013-03-13 14:01:19
tags:
---

当遇到这个问题的时候，可能我们总会在搜素引擎上搜索出各式各样的答案，而且不一定简单实用。
大多数的搜索结果都是windows软件的。

最近我发现了这样一款软件，它不是Windows平台的，它的名字叫lame，如果你用的是Linux，那么lame将助你一臂之力，
既实用又简单。

【安装】
Gentoo: emerge lame
Ubuntu: sudo apt-get install lame

【使用】
lame -h audio.wav audio.mp3

-h表示高质量的音频。
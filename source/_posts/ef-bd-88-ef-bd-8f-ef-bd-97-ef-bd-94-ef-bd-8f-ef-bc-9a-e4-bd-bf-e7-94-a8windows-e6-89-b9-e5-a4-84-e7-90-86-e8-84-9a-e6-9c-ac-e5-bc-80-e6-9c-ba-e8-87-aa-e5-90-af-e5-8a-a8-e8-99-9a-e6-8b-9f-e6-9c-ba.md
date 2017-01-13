---
title: ＨＯＷＴＯ：使用Windows批处理脚本开机自启动虚拟机
tags:
  - Gentoo
  - vbscript
  - VirtualBox
  - Windows
  - 批处理
id: 706
categories:
  - HOWTO
date: 2012-11-21 14:45:48
---

    最近在Windows 7中使用VirtualBox安装了一个Gentoo虚拟机，使用Xshell或putty远程连接虚拟机干活，所以根本没有必要看到虚拟机的界面（这个问题已经在以前的[一篇文章](http://1.sunchunman.sinaapp.com/?p=687 "后台启动VirtualBox虚拟机")中解决），但是还有一个问题：
每次Windows开机，我都必须手动在cmd下输入一长串命令开启Gentoo虚拟机，然后才能远程连接。
那么如何解决这个问题，能不能开机自启动该虚拟机？
在这里，我主要使用Windows批处理实现这个功能。
一、首先：创建批处理文件，实现启动虚拟机功能；
windows批处理文件的后缀为.bat,比如创建一个文件vBox-auto-start.bat,在该文件写入如下代码：
[bash]
::关闭回显
@echo off 
::切换到vBoxMange.exe 所在的目录
cd /d F:\VirtualBox\
::后台启动虚拟机Gentoo
VBoxManage.exe startvm Gentoo  --type vrdp
[/bash]

这样我们每次开机，只需要双击该batch文件即可启动虚拟机。

二、将该批处理文件的快捷方式加入Windows开始按钮的启动文件夹。

到这里，我们已经可以实现开机自启动虚拟机了。

但我们还可以发现个问题，开机后会有一个黑窗口弹出一闪而过。
这就是我们的批处理文件执行时的效果。

那么如何实现既能开机自启动虚拟机，又能不弹出黑窗口呢？
在这，我们可以使用vbscript来完成这个任务：
[bash]
Set ws = CreateObject(&quot;Wscript.Shell&quot;)
ws.run &quot;cmd /c vbox-auto-start.bat&quot;, vbhide
[/bash] 
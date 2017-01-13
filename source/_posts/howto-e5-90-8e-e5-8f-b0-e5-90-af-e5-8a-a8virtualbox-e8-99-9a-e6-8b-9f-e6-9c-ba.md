---
title: 'HOWTO:后台启动VirtualBox虚拟机'
tags:
  - HOWTO
  - VBoxManager
  - VirtualBox
  - 虚拟机
id: 687
categories:
  - HOWTO
  - 工具
date: 2012-11-10 07:18:59
---

VirtualBox命令行下得管理工具为VBoxManager.exe，该工具在VirtualBox安装目录的根目录下。

启动虚拟机前，我们需要了解目前VirtualBox上安装了哪些虚拟机：
[bash]
VBoxManager.exe list vms
[/bash]

**然后下面我们在后台启动虚拟机：**
[bash]
VBoxManager.exe startvm vmname --type vrdp 
[/bash]

此时，我们可以查看已经运行的虚拟机：
[bash]
VBoxManager.exe list runningvms
[/bash]

最后我们在不用该虚拟机时，我们可以关闭虚拟机：
[bash]
VBoxManager.exe controlvm vmname poweroff
[/bash]

更多命令请查看该链接[ VBoxManager.txt](http://2.sunchunman.sinaapp.com/VM/vBoxManager.txt "VBoxManager的更多命令")
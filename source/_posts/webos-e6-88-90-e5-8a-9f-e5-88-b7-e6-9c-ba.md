---
title: webOS成功刷机
tags:
  - Veer
  - webOS
  - 刷机
id: 595
categories:
  - HOWTO
  - webOS
date: 2012-06-25 05:15:50
---

**20120624 火车票预订与webOS刷机
**
20120706早上就要到北京入职，最近刚答辩结束，本想6月27日搬家时在火车票代售点购票，最后又听同事们说硬卧已经售空，然后我就不淡定了，至27号还有3天，到那时候估计连坐票都会售空，于是我也开始在12306.cn订票，陈和我一样，都还没订票，正好，听他说有两张硬卧流出，他抢订了一张，顿时，我也抓紧时间，抢购了最后一张硬卧，还和陈的硬卧挨着，真好。我只能说我真幸运。

在答辩结束后，又一事降临到我身上，年初淘到的HP Veer手机突然之间在开机时不能进入系统，每次开机就出现语言选择界面，而且屏幕的任何地方都不能触屏，不知不觉间，一款智能机变成砖块，什么也不能干（包括打电话、发短信、上网、等等）。此时，突然感觉与外界失去了联系，不能联系家人、老师、同学、朋友，不能及时接受到家人、老师、公司的电话或通知，整天都急着刷机解决手机问题，希望把手机修理好。

我刷机的要求：
1、至少不能清除USB空间的照片、音乐等数据；
2、应用程序数据可以删除，不删除更好。

在网上找了好多方法，而且自己也想了很多方法，都不行。
比如，我想通过webOS quick install 先把USB空间的数据备份到电脑上，然后重新彻底刷机，清除手机所有数据。要将USB设备空间的数据备份到电脑上，那首先要用USB线将HP Veer和电脑连接起来，我们知道，一般我们使用USB模式将HP Veer连接到电脑上时，手机会自动弹出选项，让我们选择充电模式或USB模式，要通过USB在电脑上将软件安装到webOS 设备上，还要打开开发者模式。可前面我们描述过，HP Veer一开机，即进入语言选择界面，触屏没有任何反应，所以根本就没有模式选择的选项和电话键盘页面。就这样，该方法被我试了好几次，最终被淘汰。

webOSdoctor的认识：
一开始，我对于webOS doctor的认识并不深，并没有太关注这个软件。但无奈之下，只能了解下webOS doctor，在webOS官网，我发现了对于webOS的描述：
webOS Doctor resets your device and installs the latest available version of HP webOS. It runs on a computer and transfers the update through your device's USB cable. It is an alternative to updating your device over-the-air (OTA). If your device is frozen, webOS Doctor restores functionality.

从上面的描述可以看出，webOS将重置我们的设备，而且会安装最新的webOS系统。对于我们，最重要的是最后一句话，如果你的设备变成“砖块”，那么可以使用webOS Doctor修复设备的功能。

我看见这句话时，心里高兴了很久，但是我还有个担心：就是我的照片和音乐会不会在使用webOS Doctor刷机时一起被删除。最后，我在请教HP 技术工程师Sam时，Sam给我提示了一点，在使用webOS Doctor时，系统只会重置应用数据，而且等刷机完成时，还可以登录自己的profile恢复这些应用数据，包括通讯录等数据。于是，我放心了，开始大胆尝试使用webOS Doctor。此时，我本想再联系Sam，可此时HP webOS官网给我随机分配了另一个技术工程师，在他的指导下，我在windows下尝试使用webOS Doctor刷机修复我的Veer。可试了一下午，每次刷机进度只到4%，USB连接就自动切断，此时，HP webOS技术工程师问我，有没有安装HP未验证的软件，我当然安装了，比如说人人、QQ，还有自己写的一个小程序，然后HP工程师说这可能导致未能正常刷机，让我在其他计算机上试下。

而我未选择在其他机器上重新刷机，只是选择了另一个系统，Ubuntu，我进入自己的Ubuntu，虽然自己安装了openJDK，但最后自己还是下载安装了Java 1.7，使用javaws命令打开jnlp格式的webOS Doctor下载程序（该文件的下载方法后面会介绍），然后等webOS Doctor下载完成后，运行webOS Doctor，使用USB数据线连接HP Veer和计算机，并按住关机键，连续拨动静音键三次，重启HP Veer，此时并长按声音增加键，直至Veer屏幕上出现一个大的USB图标，此时，按webOS Doctor上的指示依次操作，直至刷机成功即可。刷机后，要选择语言并输入原来的profile或重新创建profile。

注：使用webOS Doctor刷机不会删除音乐、照片等数据。

下面谈下如何下载正确的webOS Doctor。
1、首先打开链接：http://ws.hpwebos.com/webosdoctor/sorry.htm 
2、在Select your device选择Pre 2,然后输入Veer翻盖后面的SN（Serial Number）,此时提交即可下载webosdoctorp160unaatt.jnlp文件。
3、使用javaws命令打开webosdoctorp160unaatt.jnlp，即可开始下载webOS Doctor。
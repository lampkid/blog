---
title: NI MAX 为什么不能识别keithley 2001万用表
id: 590
categories:
  - HOWTO
  - LabVIEW
  - 毕业设计
date: 2012-05-23 02:43:08
tags:
---

MAX即Measurement&Automation Explore ，可用来配置和查看LabVIEW相关硬件、软件包括驱动等。
我的计算机已经能够识别GPIB卡，但是仍然不能识别仪器万用表，这是什么原因？
经咨询和查证，我将万用表的GPIB地址设为了0，我只要将GPIB地址设为其他地址，如1，MAX就能正确识别万用表了。
但是还是不明白为什么万用表GPIB地址不能设为0呢？地址0有什么特殊的用途吗？
---
title: 'HOWTO:在Gentoo虚拟机上如何正确配置网络'
tags:
  - Gentoo
  - VirtualBox
  - 网络
  - 虚拟机
id: 710
categories:
  - HOWTO
  - Linux
  - 网络
date: 2012-11-23 08:16:34
---

说下我的系统环境：

**【ENV】**

宿主机操作系统：Windows 7

虚拟软件：VirtualBox 4.2.4 r81684

虚拟机操作系统：Linux tux 3.5.7-gentoo

虚拟机网络配置：<span style="text-decoration: underline; color: #ff0000;">使用两块网卡，网卡1采用NAT配置，网卡2采用桥接方式配置。</span>

网络配置中遇到的问题

**【ISSUE】**

我在VirtualBox上安装了Gentoo虚拟机（称之为VM-OLD）后，当从该虚拟机上复制一个新的Gentoo虚拟机(VM-COPY)时：出现以下两个问题：

1、如果VM-OLD仍在运行，则此时不能启动VM-COPY；

2、如果VM-COPY已经启动，<span style="text-decoration: underline;">不能找到ethernet网口（包括eth0,eth1）</span>，除了lo网口。

下面说下问题出现的原因：

**【WHY】**

1、原来虚拟机VM-OLD已经运行，拷贝的虚拟机不能启动时，可能MAC存在冲突，请重新初始化MAC；

2、网口找不到的原因：
1）网口绑定的MAC与与网口的MAC不一致。

因为复制虚拟机时，同时也复制了原来虚拟机的配置，可以在/etc/udev/rules.d/70-persistent-net.rules文件中查看验证。如下：

[bash]
SUBSYSTEM==&quot;net&quot;, ACTION==&quot;add&quot;, DRIVERS==&quot;?*&quot;, ATTR{address}==&quot;08:00:27:2d:94:2e&quot;, ATTR{dev_id}==&quot;0x0&quot;, ATTR{type}==&quot;1&quot;, KERNEL==&quot;eth*&quot;, NAME=&quot;eth0&quot;

# PCI device 0x8086:0x100e (e1000)
SUBSYSTEM==&quot;net&quot;, ACTION==&quot;add&quot;, DRIVERS==&quot;?*&quot;, ATTR{address}==&quot;08:00:27:79:58:dc&quot;, ATTR{dev_id}==&quot;0x0&quot;, ATTR{type}==&quot;1&quot;, KERNEL==&quot;eth*&quot;, NAME=&quot;eth1&quot;
[/bash]

2）/etc/init.d/下没有创建net.eth0和net.eth1对net.lo的软连接。

**【SOLUTION】**
1、如果MAC与其他机器冲突，重新初始化MAC地址即可；
2、如果网口的MAC绑定错误，可以编辑/etc/udev/rules.d/70-persistent-net.rules,或删除该文件后重启机器（重启后会自动生成）
3、如果缺少类似net.eth0的软链接，可采用如下方法解决：
在/etc/init.d/下我们可以发现net.lo文件，如果没有该文件，从原来的虚拟机或其他机器上上拷贝一个；
如果我们没有发现类似net.eth0的文件，则使用如下命令在当前目录下创建：

[bash]
cd /etc/init.d/
ln -s net.lo net.eth0
ln -s net.lo net.eth1
[/bash]

创建net.eth0或net.eth1之后，可以使用rc-update add eth0 default将其添加到默认运行级别。
此时，检查/etc/conf.d/net配置没问题后重启eth0和eth1,如下：

[bash]
/etc/init.d/net.eth0 restart
/etc/init.d/net.eth1 restart
[/bash]

/etc/conf.d/net的配置

[plain]
config_eth0=&quot;dhcp&quot;
config_eth1=&quot;192.168.0.2 netmask 255.255.255.0 brd 192.168.0.255&quot;
routes_eth1=&quot;default via 192.168.0.1&quot;
[/plain]

**【Summary】**
网络配置：
1、网卡配置
如果使用VirtualBox或VMWare等虚拟软件，可以配置一个NAT网卡和桥接网卡；注意重新初始化MAC地址；
2、net.lo软链配置

[bash]
ln -s net.lo net.eth0
ln -s net.lo net.eth1
rc-update add eth0 default
rc-update add eth1 default
[/bash]

3、网卡与网口绑定配置
<span style="text-decoration: underline; color: #ff0000;">**删除已经存在的/etc/udev/rules.d/70-persistent-net.rules，然后重启机器即可**</span>。或编辑该文件：

[bash]
SUBSYSTEM==&quot;net&quot;, ACTION==&quot;add&quot;, DRIVERS==&quot;?*&quot;, ATTR{address}==&quot;08:00:27:2d:94:2e&quot;, ATTR{dev_id}==&quot;0x0&quot;, ATTR{type}==&quot;1&quot;, KERNEL==&quot;eth*&quot;, NAME=&quot;eth0&quot;

# PCI device 0x8086:0x100e (e1000)
SUBSYSTEM==&quot;net&quot;, ACTION==&quot;add&quot;, DRIVERS==&quot;?*&quot;, ATTR{address}==&quot;08:00:27:79:58:dc&quot;, ATTR{dev_id}==&quot;0x0&quot;, ATTR{type}==&quot;1&quot;, KERNEL==&quot;eth*&quot;, NAME=&quot;eth1&quot;
[/bash]

4、IP配置
/etc/conf.d/net的配置

[plain]
config_eth0=&quot;dhcp&quot;
config_eth1=&quot;192.168.0.2 netmask 255.255.255.0 brd 192.168.0.255&quot;
routes_eth1=&quot;default via 192.168.0.1&quot;
[/plain]

5、重启网络或重启机器
[bash]
/etc/init.d/net.eth0 restart
/etc/init.d/net.eth1 restart
[/bash] 
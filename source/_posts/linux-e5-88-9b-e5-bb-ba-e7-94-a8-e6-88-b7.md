---
title: Linux创建用户
tags:
  - Linux
  - 系统管理
id: 790
categories:
  - HOWTO
  - Linux
date: 2013-08-10 06:22:33
---

useradd newaccount -m -G 411

-m :为用户newaccount创建家目录，/home/newaccount/
-G:为用户分配用户组，411为组ID

可使用passwd为用户设置密码
---
title: '如何在命令行下导出#PostgreSQL##数据库#的表结构和数据'
tags:
  - Database
  - PostgreSQL
  - 数据库
id: 314
categories:
  - HOWTO
  - PostgreSQL
  - 数据库
date: 2012-01-13 13:30:35
---

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/01/postgresql-logo.png "postgresql-logo")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/01/postgresql-logo.png)

pg_dump命令：
===============

    pg_dump  rd -U postgres -W > /path/to/rd.sql
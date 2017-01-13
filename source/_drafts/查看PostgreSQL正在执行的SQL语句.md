---
title: 查看PostgreSQL正在执行的SQL语句
id: 773
categories:
  - HOWTO
  - 其他
tags:
---

使用以下sql语句可查看正在执行的SQL语句。
SELECT datname,procpid,query_start, current_query,client_addr FROM pg_stat_activity；

不过，要想看到SQL语句，得在postgreSQL配置文件postgesql.conf中配置以下选项：
---
title: PostgreSQL导出数据库
tags:
  - PostgreSQL
id: 859
categories:
  - HOWTO
  - PostgreSQL
  - 数据库
date: 2013-09-16 07:17:47
---

pg_dump -U username database   -t tablename  -f export.sql --role role  --inserts
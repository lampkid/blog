---
title: PostgreSQL查找某字段含有单引号记录
tags:
  - PostgreSQL
id: 783
categories:
  - HOWTO
  - PostgreSQL
date: 2013-07-09 23:58:24
---

如果某字段含有单引号，需要使用两个单引号，如''
select * from book where name = 'Chunman''Book';
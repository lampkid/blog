---
title: PostgresSQL支持正则表达式
tags:
  - PostgreSQL
id: 785
categories:
  - PostgreSQL
  - 猿说技术
date: 2013-07-10 00:01:38
---

select * from book where book_no ~ '^\d+'

从book表里选取book_no以1开头的所有记录
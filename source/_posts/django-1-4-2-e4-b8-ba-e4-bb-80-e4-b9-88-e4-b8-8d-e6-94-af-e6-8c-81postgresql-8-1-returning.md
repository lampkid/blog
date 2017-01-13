---
title: Django 1.4.2为什么不支持PostgreSQL 8.1---RETURNING
tags:
  - Django
  - PostgreSQL
  - RETURNING
id: 749
categories:
  - Django
  - PostgreSQL
  - 数据库
  - 猿说技术
date: 2012-12-16 04:09:43
---

Django 1.2、Django 1.3均支持PostgreSQL 8.1, 
Django 1.4.2支持 PostgreSQL 8.2及以上版本。

但Django 1.4.2为什么不支持 PostgreSQL 8.1?
这是为什么呢？
究其原因，来源于两方面：
**1、PostgreSQL 8.1及以下版本不支持RETURNING语句扩展：**
RETURNING语句不是SQL标准语句，是PostgreSQL对ＳＱＬ标准的扩展。
PostgreSQL 8.2才开始支持 RETURNING语句：
如下：
[sql]
INSERT INTO table [ ( column [, ...] ) ]
    { DEFAULT VALUES | VALUES ( { expression | DEFAULT } [, ...] ) [, ...] | query }
    [ RETURNING * | output_expression [ AS output_name ] [, ...] ]

举例：
INSERT INTO distributors (did, dname) VALUES (DEFAULT, 'XYZ Widgets')
   RETURNING did;
[/sql]
**2、Django 1.4.2 和Django1.3或1.2对RETURNING的处理不同**
 Django 1.3在DatabaseFeatures类对can_return_insert_id默认置为False, 而Django 1.4.2对DatabaseFeatures类的属性can_return_insert_id默认值为True.

下面我们具体了解下是怎么回事？

首先看下两个类的源码：

*   DatabaseFeatures: django/db/backends/postgresql_psycopg2/base.py
*   SQLInsertCompiler:/django/db/models/sql/compiler.py

[py]

#Django 1.4.2 的DatabaseFeatures
class DatabaseFeatures(BaseDatabaseFeatures):
    needs_datetime_string_cast = False
    can_return_id_from_insert = True  #here###############here#
    requires_rollback_on_dirty_transaction = True
    has_real_datatype = True
    can_defer_constraint_checks = True
    has_select_for_update = True
    has_select_for_update_nowait = True
    has_bulk_insert = True
    supports_tablespaces = True
    can_distinct_on_fields = True

#Django 1.3.4的DatabaseFeatures
class DatabaseFeatures(BaseDatabaseFeatures):
    needs_datetime_string_cast = False
    can_return_id_from_insert = False ####here####here###
    requires_rollback_on_dirty_transaction = True
    has_real_datatype = True
    can_defer_constraint_checks = True

#Django 的SQLInsertCompiler和Django 的DatabaseOperations两个类多处均与DatabaseFeatures的can_return_insert_id属性有关:
#如：SQLInsertCompiler的execute_sql方法：
 def execute_sql(self, return_id=False):
        assert not (return_id and len(self.query.objs) != 1)
        self.return_id = return_id
        cursor = self.connection.cursor()
        for sql, params in self.as_sql():
            cursor.execute(sql, params)
        if not (return_id and cursor):
            return
        if self.connection.features.can_return_id_from_insert: #here
            return self.connection.ops.fetch_returned_insert_id(cursor)  #here
            #上面这条语句就是利用DatabaseOperations的fetch_retured_insert_id方法
        return self.connection.ops.last_insert_id(cursor,
                self.query.model._meta.db_table, self.query.model._meta.pk.column)

[/py]

**总结：**

【解决方法】
如何让Django 1.4.2支持PostgreSQL 8.1？
1、在Django源码中判断PostgreSQL的版本，如果版本小于等于8.1，将DatabaseFeatures的can_return_insert_id属性置为False:
可在DatabaseWrapper的_cursor()方法中利用其方法_get_pg_version()获取postgreSQL的版本
或直接利用from django.db.backends.postgresql_psycopg2.version import get_version
获取postgreSQL版本。
2、升级PostgreSQL，不使用PostgreSQL 8.1.
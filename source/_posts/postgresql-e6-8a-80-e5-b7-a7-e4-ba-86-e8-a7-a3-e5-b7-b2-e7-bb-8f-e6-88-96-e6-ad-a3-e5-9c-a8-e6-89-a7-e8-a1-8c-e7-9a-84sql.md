---
title: PostgreSQL 技巧 -了解已经或正在执行的SQL
tags:
  - PostgreSQL
  - 数据库
  - 调试
id: 960
categories:
  - Django
  - HOWTO
  - PostgreSQL
date: 2014-05-26 08:09:07
---

在项目中，一直缺少不了与数据库打交道，要么是性能问题的排查，要么是一些逻辑问题排查，经常需要了解原始数据库请求中的SQL语句。

为此，特做了些PostgreSQL这方面的搜索和尝试。

因为项目中用到了Django框架，所以也会Django方面入手，了解提交给数据库的SQL语句。

再次强调：本文中讲的是技巧，不是原理，因为我也不懂原理！

**一. 对于PostgreSQL 本身来说，主要可以从下面两方面入手：**

1\. 技巧一：pg_stat_activity中可以了解当前数据库中正在执行的SQL语句

select current_query,backend_start from pg_stat_activity ;

postgresql.conf参数配置：

[html]

stats_command_string = on

[/html]

如果不打开该参数，则看不到SQL语句。

2\. 技巧二: PostgreSQL日志打印：

日志默认打印在data/pg_log/目录下

postgresql.conf参数配置

[html]

log_duration = off

log_statement = none

log_min_duration_statement = 0  # -1 is disabled, 0 logs all statements
# and their durations, in milliseconds.

redirect_stderr = on            # Enable capturing of stderr into log
# files

# These are only used if redirect_stderr is on:
log_directory = 'pg_log'        # Directory where log files are written
# Can be absolute or relative to PGDATA
log_filename = 'postgresql-log.%a' # Log file name pattern.
# Can include strftime() escapes

[/html]

参数配置完成后，记得重启数据库服务器！

**二. 从Django方面入手，也可以研究研究**

技巧一：Django中间件中处理响应时获取当前数据库连接执行的SQL语句

[python]

from django.db import connection

class SQLPrinter(object):
    def process_response(self, request, response):
        print str(connection.queries) #也可以写到文件里
        return response

[/python]

要问django怎么写中间件，请google！

技巧二：django debug toolbar

这其实不是一个技巧了，而是一个调试工具，其功能见[github](https://github.com/robhudson/django-debug-toolbar)上的说明：

[https://github.com/robhudson/django-debug-toolbar](https://github.com/robhudson/django-debug-toolbar)

具体怎么使用，我也不会，因为我还没来得及玩这个工具。感兴趣的可以试试！

Currently, the following panels have been written and are working:
> *   Django version
> *   Request timer
> *   A list of settings in settings.py
> *   Common HTTP headers
> *   GET/POST/cookie/session variable display
> *   Templates and context used, and their template paths
> *   **SQL queries including time to execute and links to EXPLAIN each query**
> *   List of signals, their args and receivers
> *   Logging output via Python's built-in logging, or via the [logbook](http://logbook.pocoo.org) module> 
> There is also one Django management command currently:> 
> 
> *   debugsqlshell: Outputs the SQL that gets executed as you work in the Python interactive shell. (See example below)
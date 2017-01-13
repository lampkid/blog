---
title: 'HOWTO:python将日期转化为时间戳'
tags:
  - HOWTO
  - Python
id: 667
categories:
  - HOWTO
  - Python
date: 2012-10-29 08:05:03
---

[py]
from datetime import datetime
#获取现在日期时间
date = datetime.now()

#获取time.struct_time类型的日期，如：
#time.struct_time(tm_year=2012, tm_mon=10, tm_mday=29, tm_hour=15, tm_min=50, tm_sec=34, tm_wday=0, tm_yday=303, tm_isdst=-1)
#struct_time.tm_year可以获取到年份，也可用struct_time[0]获取到年份
struct_time = date.timetuple()

#转化为时间戳：
import time
timestamp = time.mktime(struct_time)

#可以使用time.time()直接获取到当前时间的时间戳 
time.time()
[/py]

将时间戳转化为日期可以使用datetime.datetime.fromtimestamp()方法：
[py]
from datetime import datetime
timstamp = 138409348
date = datetime.fromtimestamp(timestamp)
[/py] 
---
title: 代码行数统计脚本
tags:
  - Bash
  - Linux
  - Shell
id: 755
categories:
  - HOWTO
  - Linux
  - Shell
date: 2012-12-25 11:38:00
---

因为小潘，我搞起了代码行数统计。
可以统计一个目录及其子目录下某一文件类型的代码行数。

[bash]
#!/usr/bin/env bash
#代码行数统计
# $1目录， $2文件类型

sum=0
line=0

for line in `find $1 -type f -name &quot;*.&quot;$2 -exec wc -l {} \; |awk '{print $1}'`;do
    sum=$[$line+$sum]
done;

echo &quot;代码行数：&quot;$sum

[/bash] 
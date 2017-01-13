---
title: '使用#shell#和sed批量修改替换文件名'
tags:
  - Linux
  - sed
  - Shell
id: 432
categories:
  - HOWTO
  - Linux
  - Shell
date: 2012-03-14 01:52:00
---

[bash]
#!/bin/bash                                                                     
for file in `ls *.html`;
do
        newname=$(echo $file|sed  's/chp/CHP/'|sed 's/sect/SECT/'|sed 's/pref/PREF/')
        echo $file
        echo $newname
        mv $file  $newname
done
[/bash]

如要批量修改下面所有文件的名称，
[html]
0596001673_pythoncook-chp-sect-1.html
0596001673_pythoncook-chp-sect-2.html
0596001673_pythoncook-chp-sect-3.html
0596001673_pythoncook-chp-sect-4.html
0596001673_pythoncook-pref--4.html
[/html]

其中最重要的是sed替换：
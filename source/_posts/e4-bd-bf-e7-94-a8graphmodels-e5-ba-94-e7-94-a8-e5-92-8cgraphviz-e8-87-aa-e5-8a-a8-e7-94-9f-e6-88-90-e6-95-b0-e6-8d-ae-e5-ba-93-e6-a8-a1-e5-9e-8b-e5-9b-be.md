---
title: 使用GraphModels应用和graphviz自动生成数据库模型图
tags:
  - Django
  - dot
  - graphviz
id: 759
categories:
  - Django
  - HOWTO
  - 数据库
date: 2013-03-27 13:58:34
---

要生成Django应用的数据库模型，只需两步：
**1\. 生成dot文件**
GraphModels是一款Django应用，可以生成django应用中数据库模型的dot文件；

python manage.py graph_models  -a > project.dot
或
python manage.py graph_models app1_name app2_name > apps.dot

**2\. 将dot文件转换为png图片或其他类型的图片**

利用graphviz的dot程序即可将dot文件转换为png或jpg或其他图片类型。

dot -Tpng project.dot test.png
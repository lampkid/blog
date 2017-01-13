---
title: 在Python中使用XPath做计数统计
tags:
  - Python
  - XML
  - XPath
id: 970
categories:
  - HOWTO
  - Python
date: 2014-07-08 13:13:30
---

在XML中，想要统计一个节点中某一子节点的个数，可以使用XPath。

&nbsp;

如：

[xml]

&lt;pages&gt;

&lt;page&gt;page1&lt;/page&gt;

&lt;page&gt;page2&lt;/page&gt;

&lt;/pages&gt;

[/xml]

若要统计pages节点下有几个page节点，可使用XPath //pages/page。代码如下：

[python]

import lxml.html as H
doc=H.docment_fromstring(xml)
count = len(doc.xpath('//pages/page'))

[/python] 
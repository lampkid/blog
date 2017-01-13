---
title: Zend Framework 布局 Layout
tags:
  - Layout
  - Zend Framework
id: 429
categories:
  - PHP
  - Zend Framework
  - 猿说技术
date: 2012-03-12 09:54:06
---

Zend Layout布局至少有以下几种方法：

**第一种方法：**
在配置文件application.ini中配置：
[php]
resources.layout.layoutPath = APPLICATION_PATH &quot;/layouts/&quot;
resources.layout.layout = &quot;main&quot;
[/php]

第一行指定布局文件的路径，第二行代码指定布局文件为main.phtml。

**第二种方法：**
在public/index.php入口文件中设置布局文件：
[php]
require_once 'Zend/Layout.php';
$layout = Zend_Layout::startMvc(array(
        'layoutPath' =&gt; APPLICATION_PATH . '/layouts',
        'layout' =&gt; 'main' 
));

$layout-&gt;setLayout('second');  
[/php]

使用Zend_Layout::startMvc()指定布局文件夹和布局文件。

还可以使用$layout->setLayout更改布局文件，动态改变布局。
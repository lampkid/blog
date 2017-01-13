---
title: SQL和Zend API分组查询
tags:
  - SQL
  - Zend Framework
  - 数据库
id: 747
categories:
  - HOWTO
  - PHP
  - PostgreSQL
  - Zend Framework
  - 数据库
date: 2012-12-08 11:47:02
---

假设有一张book表，其结构为：
[bash]
id int
name varchar(100)
category varchar(50)
[/bash]
现在要找出排名前10的分类以及具有该分类的书的数目
[sql]
select category, count(book_cat) as book_count  from book  
group by category order by book_count DESC limit 10;
[/sql]

使用Zend Framework实现：
[php]
function get_top_ten_categories(){
    $select = $this-&gt;select()-&gt;setIntergrityCheck(false)
           -&gt;from(array('book'), array('category', 'book_count'=&gt;&quot;count('category')&quot;) )
           -&gt;group(array('category') )
           -&gt;order(arrary('book_count DESC') )
           -&gt;limit(10,0);
   return $this-&gt;fetchALL($select);
}
[/php]
---
title: '#spider#使用#PHP#和#正则表达式#抓取网上图书信息, 有没有hacker'
id: 84
categories:
  - HOWTO
  - 讨论/FAQ
date: 2011-12-12 12:59:10
tags:
---

下面是要抓取的页面部分HTML文档：

[html]
&lt;h2&gt;&lt;span&gt;商品所属分类&lt;/span&gt;&lt;/h2&gt;
	&lt;div class=&quot;product_category_panel&quot;&gt;
		&lt;p class=&quot;clearfix&quot;&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.html&quot;&gt;图书&lt;/a&gt;&lt;span&gt;&amp;gt;&lt;/span&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.54.html&quot;&gt;计算机/网络&lt;/a&gt;&lt;span&gt;&amp;gt;&lt;/span&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.54.04.html&quot;&gt;操作系统/系统开发&lt;/a&gt;&lt;span&gt;&amp;gt;&lt;/span&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.54.04.03.html&quot;&gt;LINUX &lt;/a&gt;&lt;/p&gt;	&lt;/div&gt;
&lt;/div&gt;            &lt;/div&gt;
            &lt;div class=&quot;dp_sidebar&quot;&gt;
                &lt;div class=&quot;dp_sidebar_content&quot;&gt;
	&lt;div class=&quot;side_title&quot;&gt;
		&lt;h2&gt;&lt;span&gt;购买本商品的顾客还买过&lt;/span&gt;&lt;/h2&gt;
	&lt;/div&gt;
[/html]

下面是我用preg_match函数和正则表达式抓取当当网图书信息的代码：

[php]
//抓取图书种类信息
$category_pattern = '|product_category_panel&quot;&gt;\s*.*&lt;a.*&gt;.*&lt;/a&gt;.*&lt;a.*&gt;(.*)&lt;/a&gt;.*&lt;a.*&gt;(.*)&lt;/a&gt;|';

if(preg_match($category_pattern, $string, $matches))
{
    var_dump($matches);
}
[/php]

抓取结构为：
计算机/网络 和 计算机理论

现在有一个问题，就是当HTML里的图书种类不是两种的时候，上面PHP里的正则表达式就不起作用了，于是我修改了一下正则表达式：

[php]
$category_pattern = '|product_category_panel&quot;&gt;\s*.*&lt;a.*&gt;.*&lt;/a&gt;(.*&lt;a.*&gt;(.*)&lt;/a&gt;.*)+|';
[/php]

问题现在又来了，不知什么情况，我的正则表达式只能匹配最后一个图书种类，即计算机理论

[html]
array(3) {
  [0]=&gt;
  string(342) &quot;product_category_panel&quot;&gt;
		&lt;p class=&quot;clearfix&quot;&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.html&quot;&gt;图书&lt;/a&gt;&lt;span&gt;&amp;gt;&lt;/span&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.54.html&quot;&gt;计算机/网络&lt;/a&gt;&lt;span&gt;&amp;gt;&lt;/span&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.54.02.html&quot;&gt;计算机理论&lt;/a&gt;&lt;/p&gt;	&lt;/div&gt;&quot;
  [1]=&gt;
  string(117) &quot;&lt;span&gt;&amp;gt;&lt;/span&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.54.02.html&quot;&gt;计算机理论&lt;/a&gt;&lt;/p&gt;	&lt;/div&gt;&quot;
  [2]=&gt;
  string(15) &quot;计算机理论&quot;
}

[/html]

修改了好多次正则，请教@fansekey,最终是无果收场，希望有前辈能指点指点。

下面是另一段HTML，包含有个图书分类，可作为测试用例子：

[html]
 &lt;h2&gt;&lt;span&gt;商品所属分类&lt;/span&gt;&lt;/h2&gt;
    &lt;div class=&quot;product_category_panel&quot;&gt;
        &lt;p class=&quot;clearfix&quot;&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.html&quot;&gt;图书&lt;/a&gt;&lt;span&gt;&amp;gt;&lt;/span&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.22.html&quot;&gt;管理&lt;/a&gt;&lt;span&gt;&amp;gt;&lt;/span&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.22.07.html&quot;&gt;金融/投资&lt;/a&gt;&lt;span&gt;&amp;gt;&lt;/span&gt;&lt;a target=&quot;_blank&quot; href=&quot;http://list.dangdang.com/book/01.22.07.02.html&quot;&gt;货币银行学&lt;/a&gt;&lt;/p&gt;    &lt;/div&gt;
&lt;/div&gt;            &lt;/div&gt;
            &lt;div class=&quot;dp_sidebar&quot;&gt;
                &lt;div class=&quot;dp_sidebar_content&quot;&gt;

[/html] 
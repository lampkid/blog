---
title: '#Markdown# 学习笔记'
tags:
  - AsciiDoc
  - documentation
  - Markdown
  - 工具
  - 文档
id: 289
categories:
  - HOWTO
  - 工具
  - 文档创作
date: 2012-01-10 16:27:45
---

Markdown学习笔记
================

by [孙春满](http://sunchunman.sinaapp.com "攀登下一个高峰，lampkid")

Markdown是什么？
----------------

Markdown 可以将纯文本转换为HTML格式，就像我在另一篇文章提到的工具AsciiDoc一样，我们可以用简单的语法标记去创作。

**Markdown** 本身有两层含义：

>1\. Markdown是一种标记语法，就像HTML一样，只不过书写时没有HTML那么麻烦。
>2\. Markdown 本身是用**Perl**编写的一个脚本工具，可以将Markdown文本转换为HTML或XHTML。

Markdown是开源的，遵循BSD-style open source license

工具介绍：
------------
- [在线尝试 Markdown](http://daringfireball.net/projects/markdown/dingus)

- MaDe编辑器 ，Chrome浏览器的插件，可以编写Markdown, MaDe是一个可视化编辑器，所见即所得，MaDe会自动帮我们把Markdown格式转换为HTML文档。 

如何编译Markdown文档：
----------------------
Markdown.pl脚本加上--html4tags选项即可输出HTML：

    % perl Markdown.pl --html4tags foo.text

利用Markdown撰写博客：
---------------------
下载[Wordpress Markdown插件](http://michelf.com/projects/php-markdown/), 将Markdown.php拷贝到WordPress plugins目录下后激活该插件即可。 本篇博客就是用Markdown撰写的， [PHP Markdown](http://michelf.com/projects/php-markdown/)是Markdown to HTML的PHP实现。

Markdown都给我们提供了哪些标记或者说语法?
-----------------------------------------

### 段落
只要用一个或多个空行将段落隔开即可；

### 标题
标题有两种风格：
#### Setext风格
    这是一个一级标题
    =====================

    这是一个二级标题
    ---------------------
#### atx风格
    ### 这是一个三级标题
N个#号就表示N级标题，如 一级标题还可以这样写：
    # 这是一个一级标题

### 引用
顶行写，使用>符号即表示该行文本为引用文本，如：

    > 这是一行引用文本
    > 这是另一行引用文本

### 强调
使用 星号* 或 下划线_, 一个*或_ 将被转换为HTML `em`, 两个**或__ 将被转为 `strong`。

    *我* 被强调了
    __我__被强调了

### 列表
#### 无序列表
可以使用 星号* 、加号+ 、减号-来标记列表

    * One
    * Two
    * Three

    + jQuery
    + Dojo
    + Prototype

    - C/C++
    - Python
    - Lisp
    - Ruby
    - PHP

#### 有序列表
只需要 使用 序号加上 点. 后跟列表项即可。

    1\. HTML5
    2\. CSS
    3\. Javascript

#### 给列表项加上文本
    - MaDe

      Made 是一个离线的浏览器插件应用，可以实时将Markdown文本转换为HTML。

    - Vim

只要在列表项之间加上空行即可。

### 链接
#### inline风格：
使用方括号将要显示的链接文本括起来，后跟小括号，将链接地址放在小括号里面即可，链接地址不用加引号。

    这是一个[链接](http://sunchunman.sinaapp.com)。

#### reference风格
我们可以使用名字作为id来定义链接。

    这是我的[微薄][1]。

    [1]: http://weibo.com/sunchunman    "孙春满的微薄"

1 就是 链接的id，id也可以是字符串，如果id是字符串时，不区分大小写。 "孙春满的微薄" 是链接的title，可以省略。

### 图片

#### inline风格
    ！[alt text](/pah/to/img.jpg "title")

"title" 是 图片的title。

#### reference 风格
    ！[alt text][id]

    [id]: /path/to/img.jpg "title" 

我们可以发现，插入图片和链接语法非常相像。

### 代码
#### code span
如果遇到特殊符号，如实体， < 和 > ，我们可以用反引号`将<引起来。

    我强烈建议不要使用`<blink>`标签。

#### code block 

代码块的插入更简单，只需要顶行书写四个空格或一个tab，然后后跟代码即可。
[c]
    #include &lt;stdio.h&gt;
    int main()
    {
        printf(&quot;Hello Markdown&quot;);
        return 0;
    }
[/c]
参考：
--------------
- [Markdown 文档](http://daringfireball.net/projects/markdown/basics)

本篇博客采用 Markdown 撰写， 使用WordPress [PHP Markdown](http://michelf.com/projects/php-markdown/  "PHP Markdown有两个，我使用的是那个扩展的，exension")插件展示
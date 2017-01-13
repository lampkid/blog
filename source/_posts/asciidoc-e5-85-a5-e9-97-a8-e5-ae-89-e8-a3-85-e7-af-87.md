---
title: '#AsciiDoc# 入门--安装篇'
tags:
  - AsciiDoc
  - documentation
  - 工具
  - 文档
id: 260
categories:
  - HOWTO
  - 工具
  - 文档创作
date: 2012-01-09 16:13:33
---

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en">

<head>

<meta http-equiv="Content-Type" content="application/xhtml+xml; charset=UTF-8" />

<meta name="generator" content="AsciiDoc 8.6.3" />

<title>AsciiDoc 入门</title>

<style type="text/css">

/* Sans-serif font. */

h1, h2, h3, h4, h5, h6,

div.title, caption.title,

thead, p.table.header,

div#toctitle,

span#author, span#revnumber, span#revdate, span#revremark,

div#footer {

  font-family: Arial,Helvetica,sans-serif;

}

/* Serif font. */

div.sectionbody {

  font-family: Georgia,"Times New Roman",Times,serif;

}

/* Monospace font. */

tt {

  font-size: inherit;

}

body {

  margin: 1em 5% 1em 5%;

}

a {

  color: blue;

  text-decoration: underline;

}

a:visited {

  color: fuchsia;

}

em {

  font-style: italic;

  color: navy;

}

strong {

  font-weight: bold;

  color: #083194;

}

tt {

  font-size: inherit;

  color: navy;

}

h1, h2, h3, h4, h5, h6 {

  color: #527bbd;

  margin-top: 1.2em;

  margin-bottom: 0.5em;

  line-height: 1.3;

}

h1, h2, h3 {

  border-bottom: 2px solid silver;

}

h2 {

  padding-top: 0.5em;

}

h3 {

  float: left;

}

h3 + * {

  clear: left;

}

div.sectionbody {

  margin-left: 0;

}

hr {

  border: 1px solid silver;

}

p {

  margin-top: 0.5em;

  margin-bottom: 0.5em;

}

ul, ol, li > p {

  margin-top: 0;

}

ul > li     { color: #aaa; }

ul > li > * { color: black; }

pre {

  padding: 0;

  margin: 0;

}

span#author {

  color: #527bbd;

  font-weight: bold;

  font-size: 1.1em;

}

span#email {

}

span#revnumber, span#revdate, span#revremark {

}

div#footer {

  font-size: small;

  border-top: 2px solid silver;

  padding-top: 0.5em;

  margin-top: 4.0em;

}

div#footer-text {

  float: left;

  padding-bottom: 0.5em;

}

div#footer-badges {

  float: right;

  padding-bottom: 0.5em;

}

div#preamble {

  margin-top: 1.5em;

  margin-bottom: 1.5em;

}

div.tableblock, div.imageblock, div.exampleblock, div.verseblock,

div.quoteblock, div.literalblock, div.listingblock, div.sidebarblock,

div.admonitionblock {

  margin-top: 1.0em;

  margin-bottom: 1.5em;

}

div.admonitionblock {

  margin-top: 2.0em;

  margin-bottom: 2.0em;

  margin-right: 10%;

  color: #606060;

}

div.content { /* Block element content. */

  padding: 0;

}

/* Block element titles. */

div.title, caption.title {

  color: #527bbd;

  font-weight: bold;

  text-align: left;

  margin-top: 1.0em;

  margin-bottom: 0.5em;

}

div.title + * {

  margin-top: 0;

}

td div.title:first-child {

  margin-top: 0.0em;

}

div.content div.title:first-child {

  margin-top: 0.0em;

}

div.content + div.title {

  margin-top: 0.0em;

}

div.sidebarblock > div.content {

  background: #ffffee;

  border: 1px solid #dddddd;

  border-left: 4px solid #f0f0f0;

  padding: 0.5em;

}

div.listingblock > div.content {

  border: 1px solid #dddddd;

  border-left: 5px solid #f0f0f0;

  background: #f8f8f8;

  padding: 0.5em;

}

div.quoteblock, div.verseblock {

  padding-left: 1.0em;

  margin-left: 1.0em;

  margin-right: 10%;

  border-left: 5px solid #f0f0f0;

  color: #777777;

}

div.quoteblock > div.attribution {

  padding-top: 0.5em;

  text-align: right;

}

div.verseblock > pre.content {

  font-family: inherit;

  font-size: inherit;

}

div.verseblock > div.attribution {

  padding-top: 0.75em;

  text-align: left;

}

/* DEPRECATED: Pre version 8.2.7 verse style literal block. */

div.verseblock + div.attribution {

  text-align: left;

}

div.admonitionblock .icon {

  vertical-align: top;

  font-size: 1.1em;

  font-weight: bold;

  text-decoration: underline;

  color: #527bbd;

  padding-right: 0.5em;

}

div.admonitionblock td.content {

  padding-left: 0.5em;

  border-left: 3px solid #dddddd;

}

div.exampleblock > div.content {

  border-left: 3px solid #dddddd;

  padding-left: 0.5em;

}

div.imageblock div.content { padding-left: 0; }

span.image img { border-style: none; }

a.image:visited { color: white; }

dl {

  margin-top: 0.8em;

  margin-bottom: 0.8em;

}

dt {

  margin-top: 0.5em;

  margin-bottom: 0;

  font-style: normal;

  color: navy;

}

dd > *:first-child {

  margin-top: 0.1em;

}

ul, ol {

    list-style-position: outside;

}

ol.arabic {

  list-style-type: decimal;

}

ol.loweralpha {

  list-style-type: lower-alpha;

}

ol.upperalpha {

  list-style-type: upper-alpha;

}

ol.lowerroman {

  list-style-type: lower-roman;

}

ol.upperroman {

  list-style-type: upper-roman;

}

div.compact ul, div.compact ol,

div.compact p, div.compact p,

div.compact div, div.compact div {

  margin-top: 0.1em;

  margin-bottom: 0.1em;

}

div.tableblock > table {

  border: 3px solid #527bbd;

}

thead, p.table.header {

  font-weight: bold;

  color: #527bbd;

}

tfoot {

  font-weight: bold;

}

td > div.verse {

  white-space: pre;

}

p.table {

  margin-top: 0;

}

/* Because the table frame attribute is overriden by CSS in most browsers. */

div.tableblock > table[frame="void"] {

  border-style: none;

}

div.tableblock > table[frame="hsides"] {

  border-left-style: none;

  border-right-style: none;

}

div.tableblock > table[frame="vsides"] {

  border-top-style: none;

  border-bottom-style: none;

}

div.hdlist {

  margin-top: 0.8em;

  margin-bottom: 0.8em;

}

div.hdlist tr {

  padding-bottom: 15px;

}

dt.hdlist1.strong, td.hdlist1.strong {

  font-weight: bold;

}

td.hdlist1 {

  vertical-align: top;

  font-style: normal;

  padding-right: 0.8em;

  color: navy;

}

td.hdlist2 {

  vertical-align: top;

}

div.hdlist.compact tr {

  margin: 0;

  padding-bottom: 0;

}

.comment {

  background: yellow;

}

.footnote, .footnoteref {

  font-size: 0.8em;

}

span.footnote, span.footnoteref {

  vertical-align: super;

}

#footnotes {

  margin: 20px 0 20px 0;

  padding: 7px 0 0 0;

}

#footnotes div.footnote {

  margin: 0 0 5px 0;

}

#footnotes hr {

  border: none;

  border-top: 1px solid silver;

  height: 1px;

  text-align: left;

  margin-left: 0;

  width: 20%;

  min-width: 100px;

}

div.colist td {

  padding-right: 0.5em;

  padding-bottom: 0.3em;

  vertical-align: top;

}

div.colist td img {

  margin-top: 0.3em;

}

@media print {

  div#footer-badges { display: none; }

}

div#toc {

  margin-bottom: 2.5em;

}

div#toctitle {

  color: #527bbd;

  font-size: 1.1em;

  font-weight: bold;

  margin-top: 1.0em;

  margin-bottom: 0.1em;

}

div.toclevel1, div.toclevel2, div.toclevel3, div.toclevel4 {

  margin-top: 0;

  margin-bottom: 0;

}

div.toclevel2 {

  margin-left: 2em;

  font-size: 0.9em;

}

div.toclevel3 {

  margin-left: 4em;

  font-size: 0.9em;

}

div.toclevel4 {

  margin-left: 6em;

  font-size: 0.9em;

}

</style>

</head>

<body class="article">

<div id="header">

# AsciiDoc 入门

</div>

<div id="content">

<div id="preamble">

<div class="sectionbody">

<div class="admonitionblock">

<table><tr>

<td class="icon">

<div class="title">Note</div>

</td>

<td class="content">nothing</td>

</tr></table>

</div>

</div>

</div>

<div class="sect1">

## 为什么我学习AsciiDoc？

<div class="sectionbody">

<div class="paragraph">

首先，作为一个技术人，记笔记是很重要的。当然，选择一种记笔记的工具是必须的了。
</div>

<div class="paragraph">

记笔记有很多种方式，如使用纸质的笔记本，使用word文档，使用Evernote在线笔记本，使用OneNote，

使用HTML，使用Wiki、Markdown、viki、muse、DocBook、LaTex等等，有这么多的工具，而我为什么要使用AscciDoc呢？

因为我需要编辑公式，而且简单易用，因为我需要将做好的笔记上传到互联网，展示分享给大家。
</div>

</div>

</div>

<div class="sect1">

## 那就开始吧：

<div class="sectionbody">

</div>

</div>

<div class="sect1">

## AsciiDoc的安装

<div class="sectionbody">

<div class="paragraph">

Ubuntu下的安装：
</div>

<div class="listingblock">

<div class="content">

<pre><tt>sudo apt-get install asciidoc</tt></pre>

</div></div>

<div class="paragraph">

从Mercurial版本库安装：
</div>

<div class="paragraph">

先确认本地是否安装了Mercurial:
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ hg --version</tt></pre>

</div></div>

<div class="paragraph">

如果没有安装，请安装：
</div>

<div class="listingblock">

<div class="content">

<pre><tt>sudo apt-get install mercurial</tt></pre>

</div></div>

<div class="paragraph">

从Mercurial下载Asciiidoc:
</div>

<div class="paragraph">

将AsciiDoc-8.6.6下载到~/asciidoc/目录：
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ cd ~/asciidoc

$ hg clone -r 8.6.6 https://asciidoc.googlecode.com/hg/  asciidoc-8.6.6</tt></pre>

</div></div>

<div class="paragraph">

然后我们可以直接运行asciidoc
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ ~/asciidoc/asciidoc-8.6.6/asciidoc.py

$ ~/asciidoc/asciidoc-8.6.6/a2x.py</tt></pre>

</div></div>

<div class="paragraph">

是不是很麻烦，OK，做一个软链接到PATH路径里：
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ ln -s ~/asciidoc/asciidoc-8.6.6/asciidoc.py  ~/bin/asciidoc

$ ln -s ~/asciidoc/asciidoc-8.6.6/a2x.py ~/bin/a2x</tt></pre>

</div></div>

<div class="paragraph">

不仅如此，我们可以编译安装，这样计算机的每个用户都可以用asciidoc这个工具了。
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ autoconf      # create configure

$ ./configure   # 创建Makefile

$ make

$ make install  # 编译安装</tt></pre>

</div></div>

<div class="paragraph">

那我们想卸载咋办？
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ sudo make uninstall</tt></pre>

</div></div>

<div class="paragraph">

从tarball安装：
</div>

<div class="paragraph">

从http://sourceforge.net/projects/asciidoc/下载tarball源码包，然后用以下命令安装：
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ tar -xzf asciidoc-8.6.6.tar.gz

$ cd asciidoc-8.6.6

$ ./configure

$ sudo make install</tt></pre>

</div></div>

<div class="paragraph">

同样可以使用以下命令卸载AsciiDoc:
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ sudo make uninstall</tt></pre>

</div></div>

<div class="paragraph">

在vim下我们可以使用两个插件高亮AsciiDoc 语法，而且可以检测AsciiDoc文件类型:

   asciidoc.vim                    syntax 目录里

   asciidoc_filetype.vim           ftdetect目录里
</div>

<div class="paragraph">

如何在Windows上安装：

下载asciidoc-8.6.6.zip,并解压：
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ unzip asciidoc-8.6.6.zip</tt></pre>

</div></div>

<div class="paragraph">

如果要在Wndows上生成PDF等文件格式，可以参考这篇文章：http://blog.rainwebs.net/2010/02/25/how-to-create-handsome-pdf-documents-without-frustration/ How to Create Handsome PDF Documents Without Frustration using Cygwin, dblatex and AsciiDoc.
</div>

<div class="paragraph">

如何知道我们是否安装成功呢？
</div>

<div class="paragraph">

在AsciiDoc的doc目录里，又一个用户指南 ./doc/asciidoc.txt ,我们可以尝试将该asciidoc文件转换为XHTML:
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ python asciidoc.py asciidoc.txt</tt></pre>

</div></div>

<div class="paragraph">

想尝试更完整的测试吗？切换到 AsciiDoc程序根目录里，看见main.aap了吗？使用该脚本测试
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ aap test</tt></pre>

</div></div>

<div class="paragraph">

想自己build AsciiDoc的tarball、zip包、文档和AsciiDoc的demo吗？只需切换到根目录，运行aap
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ aap</tt></pre>

</div></div>

<div class="paragraph">

当然，我们也可以切换到子目录里，build自己需要的部分，如
</div>

<div class="listingblock">

<div class="content">

<pre><tt>./doc/main.aap   build 文档

./examples/website/main.aap  build 一个demo网站

./common.aap  包含在所有的脚本里,公共文件，自然其他build过程都得需要它了</tt></pre>

</div></div>

<div class="paragraph">

如果你和我一样，本身就使用的是Linxu的某个发行版，那么可以像我一样，使用Linux系统自带的软件管理包安装：
</div>

<div class="listingblock">

<div class="content">

<pre><tt>$ yum install asciidoc     # Fedora Linux</tt></pre>

</div></div>

</div>

</div>

<div class="sect1">

## Mercurial 是什么？

<div class="sectionbody">

<div class="paragraph">

一个分布式版本控制工具， git也是一个分布式版本控制工具，而SVN是一个集中式的版本控制工具。
</div>

<div class="paragraph">

具体参考：

[http://mercurial.selenic.com/](http://mercurial.selenic.com/)
</div>

</div>

</div>

<div class="sect1">

## AAP 是什么？

<div class="sectionbody">

<div class="paragraph">

该工具可以locate、下载、build和安装软件，AAP支持源代码浏览、开发程序、管理软件和文档的版本发行等等。
</div>

<div class="paragraph">

具体参考：

[http://www.a-a-p.org/](http://www.a-a-p.org/)
</div>

</div>

</div>

</div>

<div id="footnotes">

* * *
</div>

<div id="footer">

<div id="footer-text">

Last updated 2012-01-09 23:54:07 CST

</div>

</div>

</body>

</html>
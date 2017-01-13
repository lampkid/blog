---
title: LaTex如何为文档添加水印
tags:
  - Tex
  - 毕业设计
  - 水印
id: 495
categories:
  - HOWTO
  - Tex
  - 工具
  - 文档创作
  - 毕业设计
date: 2012-03-28 13:27:05
---

方法一：draftcopy包
将以下代码加在导言区：

[tex]
\usepackage[all,bottom]{draftcopy}

\draftcopyName{Copyright by MichaelBibby, 2006}{50}

\draftcopySetGrey{0.8} \draftcopyPageTransform{55 rotate}

\draftcopyPageX{80}\draftcopyPageY{-25}
[/tex]

必须使用下面的步骤编译Tex文件才能出现水印效果，不能直接使用pdflatex编译。

latex --&gt; dvi --&gt; ps --&gt; pdf

要使用pdflatex直接编译得到水印效果，可采用方法二：
方法二：使用tikz

[tex]
\usepackage{tikz}
\usepackage{eso-pic}

%定义命令
\newcommand\BackgroundPicture{%
\put(0,0){%
\parbox[b][\paperheight]{\paperwidth}{%
\vfill
\centering%
\begin{tikzpicture}[remember picture,overlay]
  \node [rotate=60,scale=10,text opacity=0.2] at (current page.center) {抢先版};\end{tikzpicture}%
\vfill
}}}

%开始在页面添加水印效果
\AddToShipoutPicture{\BackgroundPicture}

\newpage

%停止添加水印效果
\ClearShipoutPicture
[/tex]

使用pdflatex编译后，可在页面看到水印“抢先版”字样。

**注意中文水印，一定要将\newcommand命令放在\begin{CJK} \end{CJK}之间，以支持中文，避免水印乱码。**

参考：
[http://blog.sina.com.cn/s/blog_5e16f1770100gegv.html](http://blog.sina.com.cn/s/blog_5e16f1770100gegv.html)
[http://blog.sina.com.cn/s/blog_5e16f1770100l6f7.html](http://blog.sina.com.cn/s/blog_5e16f1770100l6f7.html)
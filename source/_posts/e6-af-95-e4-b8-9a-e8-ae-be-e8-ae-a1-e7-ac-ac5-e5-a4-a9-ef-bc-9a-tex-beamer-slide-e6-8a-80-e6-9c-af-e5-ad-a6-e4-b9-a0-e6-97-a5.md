---
title: '#毕业设计#第5天： Tex Beamer (Slide)技术学习日'
tags:
  - Beamer
  - LaTex
  - Tex
  - 毕业设计
id: 485
categories:
  - Tex
  - 工具
  - 文档创作
  - 毕业设计
date: 2012-03-26 03:05:13
---

2012年3月23日，打算开始翻译第二篇论文，刚翻译了一段，就有一种冲动，学习Latex制作slide。

Tex制作Slide有很多技术，如pdfscreen, prosper、beamer、 beamerposter（制作海报）、ppower4、foiltex等等，而我查了大部分资料，基本上以beamer居多，beamer以Tex命令\section为基础，定义\frame，是一个不错的选择。

而在学习过程中，为了将[这个教程](http://www.math-linux.com/spip.php?article77)（http://www.math-linux.com/spip.php?article77）制作成一个简单的slide，顺便也实践下如何制作slide，就根据别人的[模板](http://www.lampos.net/latex-presentation)开始进行修改，在整个过程中，最大的问题就是如何在Tex中插入代码，经过大量探索，可以有两种选择：

*   第一，使用verbatim包；
*   第二，使用listings包；
但是无论如何，当我使用上述两种包插入Tex代码时，编译都会出错，解决办法就是在\begin{frame}命令后加以[fragile]选项即可。

[tex]
\section{Basic presentation with Beamer}
\begin{frame}[fragile]
\frametitle{Basic presentation with Beamer}
\lstset{ language=tex,
showspaces=false,
%showtabs=false,
tabsize=4,
frame=single,
framerule=1pt,
framexleftmargin=5mm,
framexrightmargin=5mm,
framextopmargin=5mm,
framexbottommargin=5mm,
numbers=left,
%numberstyle=\small,
basicstyle=\tt,
directivestyle=\tt,
identifierstyle=\tt,
commentstyle=\tt,
stringstyle=\tt,
keywordstyle=\color{blue}\tt
}

\scriptsize

\begin{lstlisting} %[caption={Basic Example}]
\documentclass{beamer}
\usepackage[latin1]{inputenc}
\usetheme{Warsaw}
\title[Make a LaTeX presentation using Beamer]{Introduction  to Beamer\\How to make a presentation with LaTeX?}    \author{Nadir Soualem -- Astozzia}
\institute{Math-linux.com}
\date{Jule 13, 2007}
\begin{document}

\begin{frame}
\titlepage
\end{frame}

\begin{frame}{Introduction}
This is a short introduction to Beamer class.
\end{frame}

\end{document}

\end{lstlisting}
\scriptsize

\begin{verbatim}

\end{verbatim}
\end{frame}

[/tex]

可以使用\scriptsize命令控制代码字体大小。

[tex][/tex]

\section{Basic presentation with Beamer}
\begin{frame}[fragile]
\frametitle{Basic presentation with Beamer}
\scriptsize
\begin{verbatim}
\documentclass{beamer}
\usepackage[latin1]{inputenc}
\usetheme{Warsaw}
\title[Make a LaTeX presentation using Beamer]{Introduction  to Beamer\\How to make a presentation with LaTeX?}
\author{Nadir Soualem -- Astozzia}
\institute{Math-linux.com}
\date{Jule 13, 2007}
\begin{document}

\begin{frame}
\titlepage
\end{frame}

\begin{frame}{Introduction}
This is a short introduction to Beamer class.
\end{frame}

\end{document}
\end{verbatim}
\end{frame}

[tex][/tex]

附上搜集的比较经典的三个beamer教程：

*   [How to make a presentation with Latex - Introduction to Beamer ](http://www.math-linux.com/spip.php?article77)
*   [A beamer quick start   ](http://www.math.umbc.edu/~rouben/beamer/)
*   [WikiBooks Latex/Presentations    ](http://en.wikibooks.org/wiki/LaTeX/Presentations)
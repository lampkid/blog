---
title: Ubuntu上如何安装revtex4-1
tags:
  - APS
  - physics
  - revtex
  - Tex
  - 杂志
id: 456
categories:
  - HOWTO
  - Tex
  - 工具
  - 文档创作
  - 毕业设计
date: 2012-03-21 13:30:56
---

&nbsp;

**什么是REVTeX 4.1？**

REVTeX 4.1 is a set of macro packages designed to be used with LaTeX2e and is well-suited for preparing manuscripts for submission to the journals of the American Physical Society (APS) and American Institute of Physics (AIP).

REVTeX 4.1是一套宏包，用来撰写APS或AIP杂质手稿。

**怎么安装？**

将revtex4-1.zip解压，里面还有一个压缩包revtex4-1-tds.zip，解压revtex4-1-tds.zip，将tex/latex/目录下的整个revtex文件夹拷贝到/usr/share/texmf/tex/latex/目录下，执行sudo texhash命令， revtex安装完毕。

**怎么与vim下的latex-suite集成？**

在vim下安装latex-suite后，会在用户家目录/home/sunchunman/.vim/ftplugin/  生成latex-suite/templates/目录，templates文件下包含一些tex模板，如article、book等。我们需要做的就是：解压revtex4-1.zip，将revtex4-1/doc/latex/revtex/sample/目录下的aip/aiptemplate.tex和aps/apstemplate.tex两个文件拷贝到上面提到的templates/目录下即可。

**如何使用aip/aiptemplate.tex和aps/apstemplate.tex两个模板呢？**

在命令行下使用vim打开任意一个tex文件，如vim test.tex, 输入:TTemplate apstemplate 或 :TTemplate aiptemplate 即可将上面两个模板导入到当前文件。

**如何编译和预览tex文件？**

如果你使用vim 下的latexsuite，vim test.tex打开tex文件后，只需输入\ll 即可编译tex文件，生成dvi格式的文档，预览结果只需输入\lv即可。

如果使用TexLive，则可使用pdftex命令。

**如何设定生成文档的格式？**

vim test.tex后，输入:TTarget pdf或:TTarget dvi即可重新设定生成文档的格式，然后使用\ll命令编译即可。

**如何解决中文问题？**

如果你在/usr/share/texmf/tex/latex/目录下安装了CJK，则可在tex文件加入如下命令即可：

[tex]
\documentclass[aip,graphicx]{revtex4-1}                                                                            
%\documentclass[aip,reprint]{revtex4-1}

\usepackage{CJK}

\begin{document}
\begin{CJK}{UTF8}{gbsn}
文档作者、标题、摘要、正文等 \end{CJK}                                                                                                        
\end{document}
[/tex] 
---
title: '对#Python##Lisp# 产生浓厚兴趣，收集了一些资源'
tags:
  - Lisp
  - Python
  - 资源
id: 146
categories:
  - Lisp
  - Python
  - 他山之石
  - 资源
date: 2011-12-20 16:13:25
---

今天听了一个Python的讲座，对Python产生了浓厚的兴趣，六月份买的《Python基础教程》，现在只看了附录那个快速入门版和前两章，计划继续学习。其实Python一直最吸引我的是它的编程风格。

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2011/12/python-logo.gif "python-logo")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2011/12/python-logo.gif)

晚上在[图灵社区](http://www.ituring.com.cn/article/553)看到一篇对《实用Common Lisp编程》译者冰河的访谈文章，下面记录几点实在的东西和体会。

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2011/12/Lisp-logo.jpg "Lisp-logo")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2011/12/Lisp-logo.jpg)

冰河谈到C和Lisp是语言的两种极端， 现在大多数语言的设计都会取C的计算模式，然后加上Lisp的特性。

emacs的很多工具使用elisp的Lisp方言编写。

Debian系统自带有 CMU Common Lisp，Steel Bank Common Lisp，GNU Common Lisp以及GNU CLISP等环境。

Debian下的Maxima和Axiom两种数学符号计算系统采用Common Lisp编写。

_The Evolution of Lisp：一篇论文，在_CMU Common Lisp (cmucl) 的软件包文档里。

作者维护过usocket、cl-xml、cl-http、cffi等开源项目，并发起cl-net-snmp项目。

作者提到使用 _SICP_ 一书和 MIT OpenCourseWare 的配套视频来学习Lisp，SICP应该是《计算机程序的构造与解释》一书。

Lisp 方言太多，我到底该学哪种呢？ 冰河提到Common Lisp将这些Lisp方言统一起来，尽量兼容它们的。答案自然而得之。

然后我网上搜罗了下，分享几本书和关于Lisp的文章：

书籍分享：

*   《实用Common Lisp编程》
*   《计算机程序的构造与解释》
*   <a>《Common Lisp the Language, 2nd Edition》</a>
*   [ _ANSI Common Lisp_ by Paul Graham](http://www.amazon.com/exec/obidos/ISBN=0133708756/martyhallsrecomm/)
*   [ _Lisp_ by Winston and Horn](http://www.amazon.com/exec/obidos/ISBN=0201083191/martyhallsrecomm/)
*   [ _On Lisp: Advanced Techniques for Common Lisp_ by Paul Graham](http://www.amazon.com/exec/obidos/ISBN=0130305529/martyhallsrecomm/)
*   [_Object Oriented Programming in Common Lisp: A Programmers Guide to the Common Lisp Object System_ by Sonya Keene](http://www.amazon.com/exec/obidos/ISBN=0201175894/martyhallsrecomm/)
*   [ _Paradigms of AI Programming: Case Studies in Common Lisp_ by Peter Norvig](http://www.amazon.com/exec/obidos/ISBN=1558601910/martyhallsrecomm/)
文章分享：

*   [**The Evolution of Lisp**](http://dl.acm.org/citation.cfm?id=1501425)   [pdf](http://www.dreamsongs.com/NewFiles/HOPL2-Uncut.pdf)  [InfoQ   ](http://www.infoq.com/presentations/Lisp-Guy-Steele-Richard-Gabriel)
*   [The Roots Of Lisp](http://www.paulgraham.com/rootsoflisp.html)
*   [What Made Lisp Different](http://www.paulgraham.com/diff.html)
人物

*   [John McCarthy's Home Page](http://www-formal.stanford.edu/jmc/)
*   [paulgraham ](http://www.paulgraham.com/lisp.html)
*   [My Lisp Experiences and the Development of GNU Emacs](http://www.gnu.org/gnu/rms-lisp.html)   Richard Stallman
Lisp在线教程：

*   [<span style="color: red;">An Introduction and Tutorial for Common Lisp</span>](http://www.apl.jhu.edu/%7Ehall/lisp.html)
*   <span style="color: red;">[Casting SPELs in Lisp](http://www.lisperati.com/casting.html)</span>
*   [《On Lisp》](http://www.paulgraham.com/onlisp.html)
*   [Practical Common Lisp](http://gigamonkeys.com/book/)
*   可以在emacs帮助文件里学习下elisp
*   [_LISP 1.5 Primer  pdf_](http://www.softwarepreservation.org/projects/LISP/book/Weismann_LISP1.5_Primer_1967.pdf)
*   [_The Programming Language LISP: Its Operation and Applications  pdf
_](http://www.softwarepreservation.org/projects/LISP/book/III_LispBook_Apr66.pdf)
Lisp 手册

*   ["MLISP Users Manual"](http://www.softwarepreservation.org/projects/LISP/stanford/Smith-MLISP-AIM-84.pdf)
*   [_LISP I Programmers Manual_](http://history.siam.org/sup/Fox_1960_LISP.pdf)
*   [_LISP 1.5 Programmer's Manual_](http://www.softwarepreservation.org/projects/LISP/book/LISP%201.5%20Programmers%20Manual.pdf)
*   [Maclisp Reference Manual](http://web.archive.org/web/20071214064433/http://zane.brouhaha.com/%7Ehealyzh/doc/lisp.doc.txt)
*   [_InterLisp Reference Manual_](http://www.bitsavers.org/pdf/xerox/interlisp/1974_InterlispRefMan.pdf).
*   [_Kent Pitman's index of Common Lisp references_](http://www.nhplace.com/kent/CL/index.html)
*   [scheme](http://www.schemers.org/Documents/Standards/R5RS/HTML/)
*   [Common Lisp Documentation](http://www.lispworks.com/documentation/HyperSpec/Front/Contents.htm)
编码规范

*   [Tutorial on Good Lisp Programming Style](http://www.cs.umd.edu/%7Enau/cmsc421/norvig-lisp-style.pdf)
Lisp 的历史：

*   [History of Lisp](http://www-formal.stanford.edu/jmc/history/lisp/lisp.html)
*   [Lisp History](http://www8.informatik.uni-erlangen.de/html/lisp-enter.html)
*   [Oral history interview with John McCarthy](http://www.cbi.umn.edu/oh/display.phtml?id=92)
*   [History of LISP at the Computer History Museum](http://www.softwarepreservation.org/projects/LISP/)
*   ["History: Where did Lisp come from?"](http://www.cs.cmu.edu/Groups/AI/html/faqs/lang/lisp/part2/faq-doc-13.html)
开发Lisp应用工具：

*   [Listbox  ：IDE](http://common-lisp.net/project/lispbox/)
*   emacs
*   [Lisp Cabinet](http://lispcabinet.sourceforge.net/)
Lisp 论坛：

*   [Quora](http://www.quora.com/Lisp-programming-language)
IRC

*   #lisp on freenode.net
Usenet

*   [comp.lang.lisp](news://comp.lang.lisp)
FAQ

*   [Lisp FAQ](http://www.faqs.org/faqs/lisp-faq/)
[他人学习Lisp的感受](http://wiki.alu.org/RtL%20Highlight%20Film)

其他：

*   [Association of Lisp Users](http://lisp.org/)
*   [CLiki](http://cliki.net/)
*   [Common Lisp Gardeners](http://lispniks.com/cl-gardeners/)
*   [The comp.lang.lisp newsgroup](http://groups.google.com/group/comp.lang.lisp)
*   [The Association of Lisp Users](http://www.alu.org/)
*   [The Common Lisp Directory](http://www.cl-user.net/)
*   [Planet Lisp](http://planet.lisp.org/)
*   [common-lisp.net/](http://common-lisp.net/)
*   [CLISP](http://clisp.org/)
参考：

*   [图灵访谈系列之三：田春谈Lisp ](http://www.ituring.com.cn/article/553)
*   [维基百科](http://en.wikipedia.org/wiki/Lisp_%28programming_language%29)
*   [An Introduction and Tutorial for Common Lisp](http://www.apl.jhu.edu/~hall/lisp.html)
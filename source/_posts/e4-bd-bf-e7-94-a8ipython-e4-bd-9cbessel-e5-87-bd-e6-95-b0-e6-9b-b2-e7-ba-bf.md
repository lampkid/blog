---
title: 使用ipython作Bessel 函数曲线
tags:
  - ipython
  - Python
  - 科学计算
id: 425
categories:
  - HOWTO
  - Python
  - SciPy
  - 科学计算
date: 2012-03-10 12:56:26
---

[py]
[~/ipython]|72&gt; x = numpy.linspace(0,20,100)
[~/ipython]|73&gt; for n in range(4):
           |..&gt;     y = sp.jn(n,x)    
           |..&gt;     plot(x, y, label=r'$J_%s(x)$' % n)
           |..&gt;     axhline(0, color='green', label='_nolegend_')
           |..&gt;     grid()
           |..&gt;     legend()
           |..&gt;     xlabel('$x$')
           |..&gt;     title(r'Bessel functions $J_n(x)$')
           |..&gt;     
           |..&gt;     
[/py]

[caption id="attachment_426" align="aligncenter" width="800" caption="使用ipython作图"][![bessel函数曲线](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/plot-bessel.png "bessel函数曲线")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/plot-bessel.png)[/caption] 
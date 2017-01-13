---
title: 'Windows上安装ipython后启动失败,代码未高亮显示'
tags:
  - ipython
  - pyreadline
  - Python
  - setuptools
id: 690
categories:
  - HOWTO
  - Python
date: 2012-11-17 02:11:15
---

安装ipython后，启动ipython出现了两个问题：
第一：未能启动ipython；
第二：ipython界面代码语法没有高亮，且不能自动补全。

一、先来看第一个问题：为什么ipython没有启动？
启动时出现如下错误：
[bash]
C:\Python27\Scripts&gt;ipython
Traceback (most recent call last):
  File &quot;C:\Python27\Scripts\ipython-script.py&quot;, line 5, in &lt;module&gt;
    from pkg_resources import load_entry_point
ImportError: No module named pkg_resources
[/bash]

为了避免这样的错误，我们需要安装[setuptools](http://pypi.python.org/pypi/setuptools "setuptools下载地址")
至于为什么需要安装setuptools，还需要继续深入研究：

我们可以查看ipython-script.py的源码，其实我们可以使用该脚本直接启动ipython:
[py]
#!python.exe
# EASY-INSTALL-ENTRY-SCRIPT: 'ipython==0.13','console_scripts','ipython'
__requires__ = 'ipython==0.13'
import sys
from pkg_resources import load_entry_point

if __name__ == '__main__':
    sys.exit(
        load_entry_point('ipython==0.13', 'console_scripts', 'ipython')()
    )

[/py]
可以看到该启动脚本中用到了pkg_resources包，这就是为什么我们要安装setuptools

二、启动ipython后，会发现如下警告：
[bash]
C:\Python27\Scripts&gt;ipython-script.py
WARNING: Readline services not available or not loaded.WARNING: Proper color sup
port under MS Windows requires the pyreadline library.
You can find it at:
http://ipython.org/pyreadline.html
Gary's readline needs the ctypes module, from:
http://starship.python.net/crew/theller/ctypes
(Note that ctypes is already part of Python versions 2.5 and newer).

Defaulting color scheme to 'NoColor'Python 2.7.3 (default, Apr 10 2012, 23:31:26
) [MSC v.1500 32 bit (Intel)]
Type &quot;copyright&quot;, &quot;credits&quot; or &quot;license&quot; for more information.

IPython 0.13 -- An enhanced Interactive Python.
?         -&gt; Introduction and overview of IPython's features.
%quickref -&gt; Quick reference.
help      -&gt; Python's own help system.
object?   -&gt; Details about 'object', use 'object??' for extra details.

In [1]:

[/bash]

从警告里，我们很容易找到解决方法：既安装[pyreadline](http://pypi.python.org/pypi/pyreadline#downloads "pyreadline下载地址")

下一步学习深入研究计划：
1、setuptools
2、pyreadline

附：
setuptools下载地址：http://pypi.python.org/pypi/setuptools
pyreadline下载地址：http://pypi.python.org/pypi/pyreadline#downloads
---
title: 使用NumPy和SciPy做科学计算
tags:
  - NumPy
  - Python
  - SciPy
  - 科学计算
id: 420
categories:
  - Python
  - SciPy
  - 工具
  - 猿说技术
  - 科学计算
date: 2012-03-10 05:16:05
---

操作系统：
Ubuntu。

工具：
ipython
matplotlib
numpy：sudo apt-get install numpy
scipy

依赖包：
 Atlas: sudo apt-get install libatlas-base-dev 
 Blas：  sudo apt-get install libblas-dev
 lapack：sudo apt-get install liblapack-dev

依赖工具（编译用）：
sudo apt-get install g++  gfortran

**安装：**
1\. 先装编译工具：
sudo apt-get install g++  gfortran
2\. 装依赖包
3\. 装numpy和matplotlib
4\. 装scipy:
下载numpy和scipy的tar包，解压缩，cd 到 含有setup.py的目录，
运行命令：
python setup.py build --fcompiler=gnu95
sudo python setup.py install --prefix=/usr/local

**下面是一个例子**：
[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/scipy-example.png "scipy-example")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/scipy-example.png)

下面是我的运行结果：
[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/scipy-plot-300x221.png "scipy-plot")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/scipy-plot.png)

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/image.png "image")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/image.png)
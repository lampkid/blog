---
title: '在#Tex#中如何输入公式'
tags:
  - LaTex
  - Tex
id: 414
categories:
  - HOWTO
  - Tex
  - 文档创作
date: 2012-03-04 12:59:06
---

输入公式需要使用$$将公式括起来，来表示当前为Math Mode(数学模式)。

如：
输入一个字母： $x$
输入一个数： $8$
输入希腊字母： $\gamma$ 、 $\Gamma$、 $nu$、 $kappa$、 $\phi$、 $\theta$、 $epsilon$、 $rho$、 $varphi$、 $\varepsilon$
$\pi$
空集合: $\emptyset$
属于： $\in$
约等于号： $\approx$
映射： $\mapsto$
上标： $x^2$、 $x^{2y}$
下标： $x_2$、 $y_{x_2}$、 ${}_2F_3$
既有上标又有下标： $x^2_3$ 或 $x_3^2$ 、 $P_2^2$ 、 $P{}_2^2$
上标带撇号： $y_1^\prime$、 $y_2^{\prime\prime}$ 、 $y'$、 $y_2''$、 $f'[g(x)]g'(x)$ 
开平方： $\sqrt3$、 $\sqrt{x+2}$
下划线： $\underline4$
上划线： $\overline{x+y}$
开n次方： $\root n \of 2$
乘号： $x\timesy$
点号： $x\cdot z$
并集交集： $x\cup y\cap z$
子集： $x\subset y\subseteq z$
加减或减加： $x\pm y\mp z$
冒号： $f\colon A\to B$

其他：
$\hat a  \check a  \tilde a  \bar a   \vec a   \dot a$

让公式各个部分水平对齐： $\sqrt{\mathstrut a}+\sqrt{\nathstrut d}+\sqrt{\mathstrut y}$
\smash  \phantom可以更灵活地控制公式各部分的位置。

我们可以通过组合简单的公式来输入复杂的公式：
如：
$(x + y)/(x - y)$
$\gamma + \nu \in \Gamma$ 
[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/math-tex-0-300x283.png "math-tex-0")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/math-tex-0.png)
更高级的命令：$$  $$
分式： $$x+y\over x-y$$
组合： $$n\choose k$$
多项式的和： $$\sum x_n$$ 、 $\sum_{n=1}^m x_n$
积分： $\int_{-\infty}^{+\infty}$、 $$\int_{-\infty}^{+\infty}$$
      $$\int\limits_0^{\pi\over2}$$

偏微分： $$\partial x$$
[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/math-tex-1-300x278.png "math-tex-1")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/math-tex-1.png)
[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/math-tex-2.png "math-tex-2")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/03/math-tex-2.png)
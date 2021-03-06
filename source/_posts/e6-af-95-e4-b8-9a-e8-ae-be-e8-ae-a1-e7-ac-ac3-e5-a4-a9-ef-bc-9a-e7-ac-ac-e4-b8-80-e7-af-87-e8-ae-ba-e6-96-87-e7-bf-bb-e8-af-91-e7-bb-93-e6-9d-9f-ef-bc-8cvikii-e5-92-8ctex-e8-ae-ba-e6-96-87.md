---
title: "\t#毕业设计#第3天： 第一篇论文翻译结束，vikii和Tex论文排版"
tags:
  - deplate
  - FePt
  - LaTex
  - Tex
  - viki
  - Vim
  - 毕业设计
id: 458
categories:
  - Tex
  - Vim
  - 工具
  - 毕业设计
date: 2012-03-22 02:26:44
---

2012年3月21日，继续翻译论文《通过添加铜减小有序化温度》，下午翻译完论文，利用deplate编译了viki文件，顺便对生成的html文件的样式稍微进行了修改（[论文翻译](http://2.sunchunman.sinaapp.com/GraduationDesign/ReductionOfOrderingTemperatureOfAnFePtOrderedAlloyByAdditionOfCu.html)）。

在用viki编辑、编译论文时，学到了很多：

*   如何在vim中利用:digraph输入数字上标和数字下标₁²,
*   如何输入+、-、×、 ÷、 = 等运算符号，还有摄氏度符号°C等。
*   如何在viki中插入图片，#IMG:xxx.png ，还有内联图片等。
*   如何在vikii中插入引用。
*   如何在viki中插入文章作者、时间、标题等信息。
*   如何在viki中插入latex代码片段。
*   如何自己写vikii主题和模板（模板还不清楚）。
下午随即用latex对翻译的论文进行了重新排版，论文模板采用aps模板，使用revtex4-1宏包，在这个过程中，我同样学习了很多（[tex经验](http://1.sunchunman.sinaapp.com/?p=456)）：

*   如何安装第三方latex宏包？
*   如何解决中文问题？
*   如何向vim下的latexsuite添加新的模板？
*   如何改变文档布局，如两列布局？（在documentclass后添加twocolumn即可）
下面还要继续学习tex中如何插入图片，如何为图片添加题注等等，如何插入引用的参考文献。

上面都是从论文形式着手而谈，下面说说论文本身，即从论文内容出发：
论文主要讲，通过向FePt中添加Cu，可以降低晶体有序化温度，什么叫有序化呢？如bcc结构的晶体，有两种原子占据立方体体心和顶点，如果两种原子无规律地占据体心和顶点，则为无序，如果两种原子分别占据体心和顶点，即为有序。（自己的见解，正确性还等待检验）。有序化温度，就是晶体从无序向有序转变时的退火温度。什么叫退火呢？退火就是将金属加热到一定温度后然后以一定速率冷却，以改良金属的某些性质。

那为什么向FePt中添加Cu就可以降低有序化温度呢？
作者首先提出观点，然后列举了前人所提出的降低有序化温度的方法，并表示自己的方法是目前更有效的，下面作者就开始分别从四个角度说明了自己的观点：

*   第一，矫顽力同退火温度的关系；
*   第二，矫顽力同铜含量的关系；
*   第三，合金的X射线衍射曲线；
*   第四，晶体的晶格参数a和c同退火温度的关系；
最后作者在最后一段作了展望，谈到,本文提出的方法使FePtCu合金在超高密度磁记录介质领域有很大的应用前景。
对于上面四个方面的阐述，我还没有真正搞明白来龙去脉，需要继续斟酌。
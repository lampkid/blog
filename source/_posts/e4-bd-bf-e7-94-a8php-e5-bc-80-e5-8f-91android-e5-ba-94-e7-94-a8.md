---
title: '使用#PHP#开发#Android#应用'
tags:
  - Android
  - ASE
  - PFA
  - PHP
id: 112
categories:
  - Android
  - HOWTO
  - PHP
date: 2011-12-18 11:17:13
---

曾与Java搭档，而如今搭档换成了PHP、Javascript等，但又想试手Android，于是就产生了一个想法：
如何使用Javascript开发Android应用，不料上网一搜，发现[《在Android上用PHP编写应用- PFA初探](http://www.cnblogs.com/fakis/archive/2010/07/29/1976590.html)》一文，于是随着文章所叙，来到[phpforandroid官网](http://phpforandroid.net/start) 下载了[PFA](http://php-for-android.googlecode.com/files/phpforandroid_r1.apk)和[ASE](http://android-scripting.googlecode.com/files/sl4a_r3.apk)。 下面根据官网和上文谈下配置Android SDK，使其支持PHP开发Android。

**第一，确保已安装Android SDK ，而且已经创建 了AVD。**

可以使用Eclipse，也可使用命令行。我目前使用命令行；如果没有创建AVD，可以在命令行下执行android命令，打开AVD Manager，创建一个即可。

**第二，下载[PFA](http://php-for-android.googlecode.com/files/phpforandroid_r1.apk)和[ASE](http://android-scripting.googlecode.com/files/sl4a_r3.apk)**

将这两个apk文件放在Android SDK目录下的tools目录下，即emulator所在目录。

**第三，启动Android模拟器**

avd-name 为我们创建的AVD名称。

[plain] emulator @avd-name [/plain]

**第四，安装#PFA#和#ASE#**

[plain]

adb install pfa-name.apk

adb install ase-name.apk

[/plain]

**第五，安装php lib和一些demo。**

在Android模拟器上打开应用程序列表，打开PFA，选择Install 。

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2011/12/android-php-179x300.png "android-php")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2011/12/android-php.png)

**第六，运行Demo**

在Android模拟器应用程序列表里打开ASE，可以发现一些Demo，我们可以试着运行下。

可能会出现错误提示，如export之类，但不影响程序运行，官方也称该ASE为非官方版本，所以可以不予理睬。

PhpForAndroid.apk requires ASE r26\. However, r26 hasn't been released yet (latest is r25)
 so we provide an unofficial ASE build by now. Please, don't tell ASE folks about bugs 
related to this build. [Contact us](http://groups.google.com/group/php-for-android "http://groups.google.com/group/php-for-android") instead or [build](http://code.google.com/p/android-scripting/wiki/CompilingASE "http://code.google.com/p/android-scripting/wiki/CompilingASE") your own ASE 
from trunk to discard an already addressed issue.

**第七，我们可以在模拟器里直接修改PHP脚本：**

在ASE里点击运行某一个程序时，然后可以点击menu，再点击Exit/Edit即可。

还可以使用adb pull命令将脚本从模拟器down到计算机上，但我不知道哪些demo php脚本放在模拟器的哪个目录。

可以这样使用这个命令看看效果：

[plain]

adb pull /data/  ./android-data

[/plain]

**第八，发布Android应用。**

一般我们都是以apk的形式发布Android应用的。

如何将PHP Android应用打包成apk？这里有些讨论：

[使用Eclipse 或 Ant](http://code.google.com/p/android-scripting/wiki/SharingScripts#Scripts_as_APK)

[其他一些讨论](http://code.google.com/p/android-scripting/issues/detail?id=55&amp;colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary%20Stars)

**其他资源：**

[更多的PHP Android 脚本Demo](http://phpforandroid.net/manual/en/index/scripts)

[PFA API Reference](http://code.google.com/p/android-scripting/wiki/ApiReference)

[PFA slideshare](http://www.slideshare.net/ivmos/phpforandroid-en?from=ss_embed)

[Android教程--百度文库 ](http://wenku.baidu.com/view/9d382641336c1eb91a375d4a.html?from=related&amp;hasrec=1)

[在Android上编写Javascript应用](http://www.cnblogs.com/fakis/archive/2010/08/02/1976589.html) 中文版

[在Android上编写Javascript应用](http://surgeworks.com/blog/lab-mobile/iphone/starting-with-titanium-and-android)英文版

[build Mac Applications with python
](http://svn.pythonmac.org/py2app/py2app/trunk/doc/index.html)
From <acronym title="Hypertext Preprocessor">PHP</acronym> to Android, Branko Ajzele's posts:

[http://inchoo.net/android-development/from-php-to-android-the-simple-stuff-what-about-arrays/](http://inchoo.net/android-development/from-php-to-android-the-simple-stuff-what-about-arrays/ "http://inchoo.net/android-development/from-php-to-android-the-simple-stuff-what-about-arrays/")

[http://inchoo.net/android-development/from-php-to-android-the-simple-foreach-loop-example/](http://inchoo.net/android-development/from-php-to-android-the-simple-foreach-loop-example/ "http://inchoo.net/android-development/from-php-to-android-the-simple-foreach-loop-example/")

[http://inchoo.net/android-development/from-php-to-android-the-simple-stuff-intents-and-the-post-get-analogy/](http://inchoo.net/android-development/from-php-to-android-the-simple-stuff-intents-and-the-post-get-analogy/ "http://inchoo.net/android-development/from-php-to-android-the-simple-stuff-intents-and-the-post-get-analogy/")

[http://inchoo.net/android-development/from-php-to-android-the-simple-stuff-asynctask-and-the-ajax-analogy/](http://inchoo.net/android-development/from-php-to-android-the-simple-stuff-asynctask-and-the-ajax-analogy/ "http://inchoo.net/android-development/from-php-to-android-the-simple-stuff-asynctask-and-the-ajax-analogy/")

[http://inchoo.net/android-development/from-php-javascript-to-android-the-simple-stuff-yes-no-confirmation-dialog/](http://inchoo.net/android-development/from-php-javascript-to-android-the-simple-stuff-yes-no-confirmation-dialog/ "http://inchoo.net/android-development/from-php-javascript-to-android-the-simple-stuff-yes-no-confirmation-dialog/")

参考：

[《在Android上用PHP编写应用- PFA初探](http://www.cnblogs.com/fakis/archive/2010/07/29/1976590.html)》

[PFA官网](http://phpforandroid.net/manual/en/index)
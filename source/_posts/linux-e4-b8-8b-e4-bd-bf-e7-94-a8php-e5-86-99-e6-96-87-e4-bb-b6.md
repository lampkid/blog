---
title: '#Linux#下使用#PHP#写文件'
tags:
  - FAQ，讨论， 权限 ，文件
id: 12
categories:
  - HOWTO
  - PHP
  - Zend Framework
  - 讨论/FAQ
date: 2011-12-16 11:28:33
---

在linux上，使用PHP写文件，总是报错，错误提示找不到该文件或目录，
我使用fopen和file_put_contents()均没有成功。

我使用PHP的环境是Zend Framework工程，public 为index.php所在目录，public 下的.htaccess文件已经修改为：将除.css|js|img|等为后缀的文件重定向到index.php。 使用PHP文件操作函数操作的文件在public 下的js文件夹。
我修改了文件的权限，改为777，仍为成功，该文件父目录权限为755,但写文件仍未成功，文件所有人和组为root:root,我改成普通用户试了下，未果。 想改为www-data用户组，但将用户改为root:www-data和www-data:www-data都未果。是不是apache权限配置的问题，同学同样的代码，在Windows上就没问题，可以正常将数据写入文件。
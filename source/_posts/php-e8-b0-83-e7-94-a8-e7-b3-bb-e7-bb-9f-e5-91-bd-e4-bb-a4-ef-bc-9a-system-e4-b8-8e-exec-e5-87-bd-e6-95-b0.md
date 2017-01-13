---
title: '#PHP#调用系统命令： system 与 exec函数'
tags:
  - exec
  - function
  - PHP
  - system
  - 函数
  - 系统函数
id: 399
categories:
  - HOWTO
  - PHP
date: 2012-02-14 12:25:45
---

PHP如何调用系统命令：

一般可以使用两种方法：
**
system函数和exec函数**

string exec ( string $command [, array &$output [, int &$return_var ]] ) ：

*   command 为被调用的系统命令；
*   output为系统命令command执行后的标准输出；
*   return_var 为 系统命令执行后的返回状态。
*   返回值为output的最后一行。

[php]
 echo exec('whoami'); 
[/php]

**string system ( string $command [, int &$return_var ] )**

*   command 为被调用的系统命令；
*   return_var 为 系统命令执行后的返回状态。
*   返回值为output的最后一行。

[php]

&lt;?php
echo '&lt;pre&gt;';

$last_line = system('ls', $retval); 

echo '
&lt;/pre&gt;
 Last line of the output: ' . $last_line . '
 Return value: ' . $retval;
?&gt;  

[/php]

exec与system的区别：

*   exec不在终端输出command执行后的结果；
*   system在终端输出command执行后的结果,无法将命令执行后的全部结果用变量保存起来。

**参考：**

php.net
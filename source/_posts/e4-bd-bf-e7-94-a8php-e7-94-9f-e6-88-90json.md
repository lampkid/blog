---
title: '使用#PHP#生成#JSON#'
tags:
  - JSON
  - PHP
id: 91
categories:
  - HOWTO
  - PHP
date: 2011-12-13 05:17:08
---

生成JSON：
**PHP**(PHP 5 &gt;= 5.2.0, PECL json &gt;= 1.2.0)：

[php] string json_encode ( mixed $value [, int $options = 0 ] )[/php]

如：

[php]
$array = array('sun', 'chun', 'man');
echo json_encode($array).PHP_EOL;

$array = array(0 =&gt; 'sun', 1 =&gt; 'chun', 2 =&gt; 'man');
echo json_encode($array).PHP_EOL;

$array = array('0' =&gt; 'sun', '1' =&gt; 'chun', '2' =&gt; 'man');
echo json_encode($array).PHP_EOL;

$array = array(4 =&gt; 'sun', 5 =&gt; 'chun', 9 =&gt; 'man');
echo json_encode($array).PHP_EOL;

$array = array(5 =&gt; 'sun', 4 =&gt; 'chun', 9 =&gt; 'man');
echo json_encode($array).PHP_EOL;

$array = array('4' =&gt; 'sun', '5' =&gt; 'chun', '9' =&gt; 'man');
echo json_encode($array).PHP_EOL;

$array = array('a0' =&gt; 'sun', 'a1' =&gt; 'chun', 'a2' =&gt; 'man');
echo json_encode($array).PHP_EOL;

$array = array('1' =&gt; 'sun', '2' =&gt; 'chun', '3' =&gt; 'man');
echo json_encode($array).PHP_EOL;

$array = array(1 =&gt; 'sun', 2 =&gt; 'chun', 3 =&gt; 'man');
echo json_encode($array).PHP_EOL;

$array = array(0 =&gt; 'sun', 2 =&gt; 'chun', 3 =&gt; 'man');
echo json_encode($array).PHP_EOL;

$array = array(0 =&gt; 'sun', 'chun', 'man');
echo json_encode($array).PHP_EOL;
[/php]

输出：

[js]
[&quot;sun&quot;,&quot;chun&quot;,&quot;man&quot;]
[&quot;sun&quot;,&quot;chun&quot;,&quot;man&quot;]
[&quot;sun&quot;,&quot;chun&quot;,&quot;man&quot;]
{&quot;4&quot;:&quot;sun&quot;,&quot;5&quot;:&quot;chun&quot;,&quot;9&quot;:&quot;man&quot;}
{&quot;5&quot;:&quot;sun&quot;,&quot;4&quot;:&quot;chun&quot;,&quot;9&quot;:&quot;man&quot;}
{&quot;4&quot;:&quot;sun&quot;,&quot;5&quot;:&quot;chun&quot;,&quot;9&quot;:&quot;man&quot;}
{&quot;a0&quot;:&quot;sun&quot;,&quot;a1&quot;:&quot;chun&quot;,&quot;a2&quot;:&quot;man&quot;}
{&quot;1&quot;:&quot;sun&quot;,&quot;2&quot;:&quot;chun&quot;,&quot;3&quot;:&quot;man&quot;}
{&quot;1&quot;:&quot;sun&quot;,&quot;2&quot;:&quot;chun&quot;,&quot;3&quot;:&quot;man&quot;}
{&quot;0&quot;:&quot;sun&quot;,&quot;2&quot;:&quot;chun&quot;,&quot;3&quot;:&quot;man&quot;}
[&quot;sun&quot;,&quot;chun&quot;,&quot;man&quot;]
[/js]

从上面结果可以看出：
只要数组的索引为0,1,2,...或'0', '1', '2', ...,即数组索引以0或'0'开头，其他索引为自然顺序，且索引相差为1，则JSON输出为数组[], 否则为对象{}.

PHP 的json_encode函数第二个参数决定数组中哪类字符串需要编码，如

[plain]
JSON_HEX_QUOT, 双引号
JSON_HEX_TAG, XML标签
JSON_HEX_AMP, 实体
JSON_HEX_APOS, 单引号
JSON_NUMERIC_CHECK,
JSON_PRETTY_PRINT,
JSON_UNESCAPED_SLASHES,
JSON_FORCE_OBJECT,
JSON_UNESCAPED_UNICODE， unicode字符
[/plain]

参考：
http://cn2.php.net/json_encode
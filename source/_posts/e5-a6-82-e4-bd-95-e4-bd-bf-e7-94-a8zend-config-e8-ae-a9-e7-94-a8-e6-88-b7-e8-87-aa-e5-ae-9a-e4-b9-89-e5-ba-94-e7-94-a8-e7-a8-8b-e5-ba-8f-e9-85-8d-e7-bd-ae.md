---
title: '如何使用#Zend_Config#让用户自定义应用程序配置'
tags:
  - PHP
  - Zend Framework
id: 167
categories:
  - HOWTO
  - PHP
  - Zend Framework
date: 2011-12-25 05:03:41
---

Zend_Config是Zend Framework的一个组件，Zend_Config可以读写数组、INI、XML格式的文件。

**我们先看一个XML的例子：**

XML文件:config.xml

[xml]
&lt;?xml version='1.0'?&gt;
&lt;config&gt;
  &lt;dialer&gt;
    &lt;number&gt;12345678&lt;/number&gt;
    &lt;retries&gt;15&lt;/retries&gt;
    &lt;protocol&gt;ppp&lt;/protocol&gt;
  &lt;/dialer&gt;
&lt;/config&gt;
[/xml]

下面看下Zend_Config是怎么访问这个XML文件的数据的：

[php]
&lt;?php
// include auto-loader class
require_once 'Zend/Loader/Autoloader.php';

// register auto-loader
$loader = Zend_Loader_Autoloader::getInstance();

// read XML config file
$config = new Zend_Config_Xml('config.xml', 'dialer');

// access individual nodes
printf(&quot;Number: %s \r\n&quot;, $config-&gt;number);
printf(&quot;Retries: %s \r\n&quot;, $config-&gt;retries);
printf(&quot;Protocol: %s \r\n&quot;, $config-&gt;protocol);
?&gt;
[/php]

其中，Zend_Loader_Autoloader可以自动加载我们要使用的Zend Framework 组件类，如Zend_Config_Xml。
我们可以使用Zend_Config，也可以使用Zend_Config的子类操作配置文件：
包括Zend_Config_Xml、Zend_Config_Ini、Zend_Config_Json、Zend_Config_Yaml,
如果要操作数组，我们可以直接使用Zend_Config.
上面的代码使用了Zend_Config_Xml,我们看下Zend_Config_Xml的构造方法：

[php]
__construct( string $xml,  //XML字符串或XML文件名
mixed $section = null,   //开始解析的XML节点
array|boolean $options = false  //设置是否允许修改该XML
) : void
[/php]

### 对于构造方法的第三个参数，需要强调一点：
如果该参数为boolean类型，即true或false，则等价于`
`

[php]
$options = array( 'allowModifications' =&gt; false）&lt;/code&gt;
[/php]

如果该参数为数组，其形式为

[php]
$options = array( 'allowModifications' =&gt; false, 'skipExtends' =&gt; false );
[/php]

不理解skipExtends的作用。

**从构造方法里可以看出，后两个参数是可选的：**

[php]

&lt;?php
// include auto-loader class
require_once 'Zend/Loader/Autoloader.php';

// register auto-loader
$loader = Zend_Loader_Autoloader::getInstance();

// read XML config file
$config = new Zend_Config_Xml('config.xml');

// access individual nodes
printf(&quot;Number: %s \r\n&quot;, $config-&gt;dialer-&gt;number);
printf(&quot;Retries: %s \r\n&quot;, $config-&gt; dialer-&gt;retries);
printf(&quot;Protocol: %s \r\n&quot;, $config-&gt; dialer-&gt;protocol);
?&gt;

[/php]

在上面的XML文件里，我们发现这些节点都没有属性，如果节点有属性，Zend_Config_Xml是怎么处理的呢？

[xml]
&lt;?xml version='1.0'?&gt;
&lt;config&gt;
  &lt;firewall context=&quot;default&quot; access=&quot;deny&quot; &gt;
    &lt;rule access=&quot;allow&quot; network=&quot;10.0.0.0/8&quot; /&gt;
    &lt;rule access=&quot;allow&quot; host=&quot;192.168.1.17&quot; /&gt;
  &lt;/firewall&gt;
&lt;/config&gt;
[/xml]

&nbsp;

[php]

&lt;?php
// include auto-loader class
require_once 'Zend/Loader/Autoloader.php';

// register auto-loader
$loader = Zend_Loader_Autoloader::getInstance();

// read XML config file
$config = new Zend_Config_Xml('config.xml', 'firewall');

// returns 'default'
echo $config-&gt;context;
// returns 'allow'
echo $config-&gt;rule-&gt;{0}-&gt;access;
// returns '192.168.1.17'
echo $config-&gt;rule-&gt;{1}-&gt;host;
?&gt;
[/php]

可以看出，节点的属性也将作为子节点处理，注意rule标签的访问，可以使用{0}、{1}分别访问rule标签。

### **读取INI文件**

INI文件：config.ini

[plain]
[dialer]
number = 12345678
retries = 15
protocol = ppp

[/plain]

&nbsp;

[php]
&lt;?php
// read XML config file
$config = new Zend_Config_Ini('config.ini', 'dialer');

// access individual elements
printf(&quot;Number: %s \r\n&quot;, $config-&gt;number);
printf(&quot;Retries: %s \r\n&quot;, $config-&gt;retries);
printf(&quot;Protocol: %s \r\n&quot;, $config-&gt;protocol);
?&gt;
[/php]

读取数组：config.php

[php]
&lt;?php
return $config = array(
  'dialer' =&gt; array(
    'number'    =&gt; 12345678,
    'retries'   =&gt; 15,
    'protocol'  =&gt; 'ppp'
  )
);
?&gt;
[/php]

&nbsp;

[php]
&lt;?php
// include PHP configuration data
require_once 'config.php';

// read XML config file
$config = new Zend_Config($config);

// access individual elements
printf(&quot;Number: %s \r\n&quot;, $config-&gt;dialer-&gt;number);
printf(&quot;Retries: %s \r\n&quot;, $config-&gt;dialer-&gt;retries);
printf(&quot;Protocol: %s \r\n&quot;, $config-&gt;dialer-&gt;protocol);
?&gt;
[/php]

使用数组的优点：
APC等PHP opcode cache可以缓冲这些数据，减少文件读操作，这样可以改善性能。

### ** 读取yaml**

参考[ two](http://www.emanaton.com/code/php/zendconfigyml) [approaches](http://blog.eval.ca/2008/02/18/using-yaml-with-the-zend-framework/), which make use of [the syck extension](http://pecl.php.net/syck) and [the spyc library](http://spyc.sourceforge.net/) 。

### ** 读取多层嵌套的配置文件**

config.xml

[xml]
&lt;?xml version='1.0'?&gt;
&lt;configs&gt;
  &lt;config scope=&quot;php&quot;&gt;
    &lt;filters&gt;
      &lt;filter name=&quot;Tidy&quot;&gt;
        &lt;parameters name=&quot;tidy_options&quot;&gt;
          &lt;parameter&gt;
            &lt;name&gt;output-xhtml&lt;/name&gt;
            &lt;value&gt;true&lt;/value&gt;
          &lt;/parameter&gt;
          &lt;parameter&gt;
            &lt;name&gt;numeric-entities&lt;/name&gt;
            &lt;value&gt;true&lt;/value&gt;
          &lt;/parameter&gt;
          &lt;parameter&gt;
            &lt;name&gt;encoding&lt;/name&gt;
            &lt;value&gt;utf8&lt;/value&gt;
          &lt;/parameter&gt;
        &lt;/parameters&gt;
      &lt;/filter&gt;
    &lt;/filters&gt;
  &lt;/config&gt;
&lt;/configs&gt;
[/xml]

&nbsp;

[php]
&lt;?php

// read XML config file
$config = new Zend_Config_Xml('config.xml', 'config');

// returns 'true'
echo $config-&gt;filters-&gt;filter-&gt;parameters-&gt;parameter-&gt;{0}-&gt;value;
?&gt;
[/php]

Zend_Config实现了迭代器，Iterator interface,所以可以迭代访问配置数据

[php]
&lt;?php
// read XML config file
$config = new Zend_Config_Xml('config.xml', 'config');

// iterate over parameters
foreach ($config-&gt;filters-&gt;filter-&gt;parameters-&gt;parameter as $p) {
  printf(&quot;%s = %s \r\n&quot;, $p-&gt;name, $p-&gt;value);
}
?&gt;
[/php]

### ** 配置之间可以继承**

XML使用extends属性，指定要继承的节点

[xml]
&lt;?xml version='1.0'?&gt;
&lt;configs&gt;
  &lt;default&gt;
    &lt;log&gt;
      &lt;filename&gt;general.log&lt;/filename&gt;
      &lt;data&gt;time,message,code&lt;/data&gt;
      &lt;maxsize&gt;2M&lt;/maxsize&gt;
    &lt;/log&gt;
  &lt;/default&gt;
  &lt;error extends=&quot;default&quot;&gt;
    &lt;log&gt;
      &lt;filename&gt;error.log&lt;/filename&gt;
    &lt;/log&gt;
  &lt;/error&gt;
&lt;/configs&gt;

[/xml]

[php]
&lt;?php
// define Zend_Config objects
$config = new Zend_Config_Xml('config.xml');

// returns 'error.log'
echo $config-&gt;error-&gt;log-&gt;filename;

// returns '2M'
echo $config-&gt;error-&gt;log-&gt;maxsize;
?&gt;
[/php]

INI使用colon冒号指定继承关系，回忆下Zend Framework工程文件中的配置文件application.ini

[plain]
[default]
log.filename = &quot;general.log&quot;
log.data = &quot;time,message,code&quot;
log.maxsize = &quot;2M&quot;

[error : default]
log.filename = &quot;error.log&quot;
[/plain]

我们还可以将配置文件分成多个配置文件，新的数据将覆盖原来的数据：

[php]
&lt;?php
// define Zend_Config objects
$zca = new Zend_Config(array('a'=&gt;10, 'b'=&gt;2), true);
$zcb = new Zend_Config(array('c'=&gt;4,  'b'=&gt;16), true);

// merge objects
$zca-&gt;merge($zcb);

// check merged data
echo $zca-&gt;a; // 10
echo $zca-&gt;b; // 16
echo $zca-&gt;c; // 4
?&gt;

[/php]

### ** 配置文件的写操作**

使用Zend_Config_Writer可以操作INI、XML、PHP Array。
INI举例：

[php]
&lt;?php

// define configuration array
$data = array(
  'name' =&gt; 'Zerg Ultralisk',
  'endurance' =&gt; '7',
  'strength' =&gt; '13',
  'intelligence' =&gt; '8',
  'damage' =&gt; '4'
);

// write INI config file
try {
  $config = new Zend_Config_Writer_Ini();
  $config-&gt;write('my.ini', new Zend_Config($data));
  echo 'Configuration successfully written to file.';
} catch (Exception $e) {
  die('ERROR: ' . $e-&gt;getMessage());
}
?&gt;
[/php]

我们使用Zend_Config_Writer_Ini的write()方法将$data写入my.ini文件。

要将配置数据写入XML文件，只需使用Zend_Config_Writer_Xml

[php]
&lt;?php

// define configuration array
$data = array(
  'name' =&gt; 'Zerg Ultralisk',
  'endurance' =&gt; '7',
  'strength' =&gt; '13',
  'intelligence' =&gt; '8',
  'damage' =&gt; '4'
);

// write XML config file
try {
  $config = new Zend_Config_Writer_Xml();
  $config-&gt;write('my.xml', new Zend_Config($data));
  echo 'Configuration successfully written to file.';
} catch (Exception $e) {
  die('ERROR: ' . $e-&gt;getMessage());
}
?&gt;
[/php]

同样，我们也可以将配置数据写入php文件，使用PHP array保存

[php]
&lt;?php

// define configuration array
$data = array(
  'name' =&gt; 'Zerg Ultralisk',
  'endurance' =&gt; '7',
  'strength' =&gt; '13',
  'intelligence' =&gt; '8',
  'damage' =&gt; '4'
);

// write array config file
try {
  $config = new Zend_Config_Writer_Array();
  $config-&gt;write('my.php', new Zend_Config($data));
  echo 'Configuration successfully written to file.';
} catch (Exception $e) {
  die('ERROR: ' . $e-&gt;getMessage());
}
?&gt;
[/php]

### **创建嵌套的XML配置文件**

使用数组初始化Zend_Config：

[php]
&lt;?php

// define configuration array
$data = array(
  'global' =&gt; array(
    'smtp' =&gt; array(
      'parameters'  =&gt; array(
        'host'      =&gt; 'smtp.example.com',
        'port'      =&gt; '587',
        'username'  =&gt; 'jeky11',
        'password'  =&gt; 'hyd3',
        'security'  =&gt; 'tls',
      )
    )
  )
);

// write XML config file
try {
  $config = new Zend_Config_Writer_Xml();
  $config-&gt;write('my.xml', new Zend_Config($data));
  echo 'Configuration successfully written to file.';
} catch (Exception $e) {
  die('ERROR: ' . $e-&gt;getMessage());
}
?&gt;

[/php]

使用object-&gt;property初始化Zend_Config

[php]
&lt;?php

// define configuration array
$data = array(
  'global' =&gt; array(
    'smtp' =&gt; array(
      'parameters'  =&gt; array(
        'host'      =&gt; 'smtp.example.com',
        'port'      =&gt; '587',
        'username'  =&gt; 'jeky11',
        'password'  =&gt; 'hyd3',
        'security'  =&gt; 'tls',
      )
    )
  )
);

// write XML config file
try {
  $config = new Zend_Config_Writer_Xml();
  $config-&gt;write('my.xml', new Zend_Config($data));
  echo 'Configuration successfully written to file.';
} catch (Exception $e) {
  die('ERROR: ' . $e-&gt;getMessage());
}
?&gt;

[/php]

### **创建嵌套的INI配置文件**

使用SetNestSeparator()设置嵌套的分隔符：

[php]
&lt;?php

// define configuration array
$data = array(
  'global' =&gt; array(
    'smtp' =&gt; array(
      'parameters'  =&gt; array(
        'host'      =&gt; 'smtp.example.com',
        'port'      =&gt; '587',
        'username'  =&gt; 'jeky11',
        'password'  =&gt; 'hyd3',
        'security'  =&gt; 'tls',
      )
    )
  ),
  'local' =&gt; array(
    'version' =&gt; '1.1'
  )
);

// write INI config file
try {
  $config = new Zend_Config_Writer_Ini();
  $config-&gt;setNestSeparator('::');
  $config-&gt;write('my.ini', new Zend_Config($data));
  echo 'Configuration successfully written to file.';
} catch (Exception $e) {
  die('ERROR: ' . $e-&gt;getMessage());
}
?&gt;
[/php]

使用setRenderWithoutSections() 将INI文件分为多个模块：

[php]
&lt;?php
// include auto-loader class
require_once 'Zend/Loader/Autoloader.php';

// register auto-loader
$loader = Zend_Loader_Autoloader::getInstance();

// define configuration array
$data = array(
  'global' =&gt; array(
    'smtp' =&gt; array(
      'parameters'  =&gt; array(
        'host'      =&gt; 'smtp.example.com',
        'port'      =&gt; '587',
        'username'  =&gt; 'jeky11',
        'password'  =&gt; 'hyd3',
        'security'  =&gt; 'tls',
      )
    )
  ),
  'local' =&gt; array(
    'version' =&gt; '1.1'
  )
);

// write INI config file
try {
  $config = new Zend_Config_Writer_Ini();
  $config-&gt;setNestSeparator('::');
  $config-&gt;setRenderWithoutSections(true);
  $config-&gt;write('my.ini', new Zend_Config($data));
  echo 'Configuration successfully written to file.';
} catch (Exception $e) {
  die('ERROR: ' . $e-&gt;getMessage());
}
?&gt;
[/php]

相关文章：应用Zend_Config创建一个用户可以自定义的Task Manager(任务管理应用)

参考：

*   [Manipulating Configuration Data with Zend_Config](http://devzone.zend.com/1792/manipulating-configuration-data-with-zend_config/)
*   [Zend Framework Reference Guide](http://framework.zend.com/manual/en/zend.config.introduction.html)
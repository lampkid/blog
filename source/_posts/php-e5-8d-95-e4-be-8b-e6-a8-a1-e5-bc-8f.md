---
title: '#PHP# #单例模式#'
id: 380
categories:
  - PHP
  - 猿说技术
  - 设计模式
date: 2012-02-01 08:49:00
tags:
---

<pre>    class SingletonClass {
        // singleton instance
        private static $instance;

        //private constructor function
        //to prevent external instantiation
        private  function __construct(){}

        //getInstance method
        public static function getInstance() {

            if(!self::$instance) {
                self::$instance = new self();
            }

            return self::$instance;
        }

        public function run() {
            print "run...\n";
        }
    }

    $className = "SingletonClass";
    $instance = SingletonClass::getInstance();
    $instance = $className::GetInstance();
    $instance = $className::getInstance();
    //都可以执行成功，php类的方法名难道不区分大小写。

    $instance = SingletonClass::getInstance();

    $instance-&gt;run();

    //js里有eval，php里也有，都可以执行代码
    eval('$instance1 = '.$className.'::GetInstance();');
    $instance1-&gt;run();</pre>
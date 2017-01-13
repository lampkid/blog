---
title: Zend Framework 实现Windows域认证
tags:
  - AD
  - LDAP
  - PHP
  - Windows
  - Zend Framework
id: 721
categories:
  - HOWTO
  - PHP
  - Zend Framework
date: 2012-11-28 11:02:24
---

一、Zend Framework验证API：
1、Zend_Auth
   Zend_Auth::getInstance()
   Zend_Auth::auhenticate($adapter)
   Zend_Auth::hasIdentity()
2、Zend_Auth_Adapter_Ldap
   Zend_Auth_Adapter_Ldap::getAccountObject()

二、如何使用Zend_Auth_Adapter_Ldap实现windows域认证
1、windows域服务器配置 
配置文件ldap.ini
[plain]
[product]
;ldap日志配置
;ldap.log_path = /tmp/ldap.log

ldap.server1.host =  192.168.10.103
;设置您服务器的域
ldap.server1.accountDomainNameShort = wp
;不使用SSL连接
ldap.server1.useSsl = false
ldap.server1.baseDn = &quot;OU=personalblog,DC=sunchunman,DC=sinapp,DC=com&quot;
;windows AD需设置bindRequiresDn为false
ldap.server1.bindRequiresDn = false
[/plain]

2、验证代码：
[php]

function validate_user_from_windows_ad(username, passwd)
{
        //获取ldap配置
        $ldap_config_file = APPLICATION_PATH . '/configs/ldap.ini';
        $ldap_config = new Zend_Config_Ini($ldap_config_file, 'production');
        //$log_path = $ldap_config-&gt;ldap-&gt;log_path;
        $ldap_options = $ldap_config-&gt;ldap-&gt;toArray();

        //unset($ldap_options['log_path']);

            // $authAdapter = new Zend_Auth_Adapter_DbTable($db);
            // 创建ldap验证适配器
            $authAdapter = new Zend_Auth_Adapter_Ldap($ldap_options, $user_name, $user_passwd_input);

            $auth = Zend_Auth::getInstance();
            //在windows域验证用户
            $auth_result = $auth-&gt;authenticate($authAdapter);

            if($auth_result-&gt;isValid()) //如果认证成功
            {

                $ldap_user = $authAdapter-&gt;getAccountObject(); //返回的对象不包含密码
                //$username = $authAdapter-&gt;getUsername(); //获取的为用户输入的用户名
                //$username = $ldap_user-&gt;samaccountname;  //获取用户的帐号名
                if($auth-&gt;hasIdentity()) //成功登录
                {
                   //验证成功后，做其他操作
                   //todo...
                   return $ldap_user;
                }

           }
}

[/php] 
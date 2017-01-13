---
title: '#PHP#$:如何使用#Zend_Mail# 发送邮件'
tags:
  - PHP
  - Zend Framework
id: 187
categories:
  - HOWTO
  - PHP
  - Zend Framework
date: 2011-12-27 11:46:31
---

[php]
&lt;?php                 
class Lampkid_Mail     
{                     
    protected $mail ; 
    public function __construct()
    {                 
        //set_time_limit(0); //不限制时间

        $sender = &quot;xxx@gmail.com&quot;; //发件人邮箱
        $smtp = 'smtp.gmail.com';  //SMTP服务器

        $account = &quot;XXX&quot;;  //邮箱帐号，即@gmail.com前面的那部分
        $display_name = &quot;要显示的发送人姓名或昵称&quot;;
        $password = &quot;&quot;; //发件人邮箱的密码

        $this-&gt;mail = new Zend_Mail(&quot;UTF-8&quot;);
        /*
         * 使用用户名密码验证帐号
         * 特别要注意你的SMTP使用的连接方式，有可能是ssl或tls
         */
        $config = array('auth' =&gt; 'login',     
        'username' =&gt; $account,
        'password' =&gt; $password,
        'ssl' =&gt; &quot;ssl&quot;   
        );            

        $transport = new Zend_Mail_Transport_Smtp($smtp, $config);
        $this-&gt;mail-&gt;setDefaultTransport($transport);

        $this-&gt;mail-&gt;setFrom($sender, $display_name);

    }                 

    //$to 可以是一个email地址数组，也可以是一个email地址
    public function send($to, $subject, $content,$has_attach=false, $attach='' )
    {                 
        $this-&gt;mail-&gt;setSubject(&quot;=?UTF-8?B?&quot;.base64_encode($subject).&quot;?=&quot;);
        $this-&gt;mail-&gt;setBodyHtml($content);
        $this-&gt;mail-&gt;addTo($to,'Test');

        //可以增加附件        
        if( true  == $has_attach)
        {             
            $mine_type = &quot;image/png&quot;;
            $this-&gt;mail-&gt;createAttachment(file_get_contents($attach), $mine_type,
 Zend_Mime::DISPOSITION_INLINE,
                Zend_Mime::ENCODING_BASE64);
        }             

        $this-&gt;mail-&gt;send();
    }                 
}                     

[/php]

参考：
[Zend Framework Reference Guide
](http://framework.zend.com/manual/en/zend.mail.multiple-emails.html)
[Zend China](http://www.zendchina.net/?action-viewnews-itemid-1323)
[叫我吹水，别叫我西门 百度博客](http://hi.baidu.com/zhangsilly/blog/item/5088742d56487137359bf753.html)
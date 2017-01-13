---
title: 使用benchSMS短信平台发送短信
tags:
  - Python
  - SMS
id: 852
categories:
  - HOWTO
  - Python
date: 2013-09-12 12:49:10
---

urlencode是为了解决短信内容为中文的问题。

accesskey 和secretkey要在http://sms.benchtech.cn申请。

[python]

from urllib import urlencode, urlopen
def send_sms(access_key, secret_key, receiver, msg):
    url = &quot;http://sms.bechtech.cn/Api/send/data/json?&quot;
    data = { &quot;accesskey&quot;: access_key,
             &quot;secretkey&quot;:secret_key,
             &quot;mobile&quot;:receiver,
             &quot;content&quot;:msg}
    data = urlencode(data)
    url = url+data
    handle = urlopen(url)
    ret = handle.read()
    dict_ret = eval(ret)
    return dict_ret

if __name__ == '__main__':
    access_key = 'xxx'
    secret_key = 'xxxxxxxxxxxxxxxxxxx'
    receiver = &quot;phone,phone,phone&quot; //多个手机号用逗号隔开。
    msg = &quot;hello, 石榴季节， 吃石榴了，哈哈,欢迎访问lilangyu.com&quot;
    ret = send_sms(access_key, secret_key, receiver, msg)
    if ret.get('result', None) == '01':
        print 'send success'

[/python] 
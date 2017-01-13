---
title: 到底什么是Web Service？
id: 1030
categories:
  - Web
  - 技术
  - 猿说技术
date: 2015-03-31 10:50:09
tags:
---

到底什么是Web Service ？

一开始对这个问题很是疑惑，以为网站只有使用到SOAP、WSDL等的技术，才以为这个网站支持Web Service。

以为一个网站仅仅使用HTTP协议 的GET、POST请求为第三方提供服务接口，不属于Web Service的范畴。

&nbsp;

最近在网上搜罗了一筐后发现，Web Service其实很简单，以上两个疑问中所谈及的均属于Web Service。

&nbsp;

维基百科里，是这样描述的：http://en.wikipedia.org/wiki/Web_service

“A **Web service** is a method of communication between two electronic devices over a [network](http://en.wikipedia.org/wiki/Computer_network "Computer network"). It is a software function provided at a network address over the Web with the service _always on_ as in the concept of [utility computing](http://en.wikipedia.org/wiki/Utility_computing "Utility computing").”

Web Service是两个电子电子设备在网络上通信的方式。

&nbsp;

W3C是这样定义Web Service的：（http://www.w3.org/TR/2004/NOTE-ws-arch-20040211/#whatis）

a software system designed to support [interoperable](http://en.wikipedia.org/wiki/Interoperability "Interoperability") machine-to-machine interaction over a [network](http://en.wikipedia.org/wiki/Computer_network "Computer network").

Definition: A Web service is a software system designed to support interoperable machine-to-machine interaction over a network. It has an interface described in a machine-processable format (specifically WSDL). Other systems interact with the Web service in a manner prescribed by its description using SOAP messages, typically conveyed using HTTP with an XML serialization in conjunction with other Web-related standards.

Web Service是为广域网上不同设备实现相互交互而设计的软件系统。

这里说的应该是传统的Web Service， 即基于SOAP协议的Web Service，即我上面所提到的第一个疑问。

&nbsp;

而现在大部分开放平台，大多使用符合REST风格的API接口对外提供Web Service。这就是我所提到的第二个疑问。

&nbsp;

个人觉得，Web Service 是一个很笼统的概念，只要通过Web向第三方提供服务，均属于Web Service。

**从****Web Service****在传统和现代的实际使用中来看包括**：

1.  基于SOAP 和HTTP协议的Web Service；
2.  符合REST风格完全基于HTTP协议的Web Service。
**可以根据一些例子来看下：**

关于基于SOAP协议的例子可以看天气的Web Service：[http://www.webxml.com.cn/WebServices/WeatherWebService.asmx?wsdl](http://www.webxml.com.cn/WebServices/WeatherWebService.asmx?wsdl)

符合REST风格完全只基于HTTP协议的例子可以看下各大开放平台：

1.  百度翻译API：[http://developer.baidu.com/wiki/index.php?title=%E5%B8%AE%E5%8A%A9%E6%96%87%E6%A1%A3%E9%A6%96%E9%A1%B5/%E7%99%BE%E5%BA%A6%E7%BF%BB%E8%AF%91/%E7%BF%BB%E8%AF%91API](http://developer.baidu.com/wiki/index.php?title=%E5%B8%AE%E5%8A%A9%E6%96%87%E6%A1%A3%E9%A6%96%E9%A1%B5/%E7%99%BE%E5%BA%A6%E7%BF%BB%E8%AF%91/%E7%BF%BB%E8%AF%91API "%E5%B8%AE%E5%8A%A9%E6%96%87%E6%A1%A3%E9%A6%96%E9%A1%B5/%E7%99%BE%E5%BA%A6%E7%BF%BB%E8%AF%91/%E7%BF%BB%E8%AF%91API")
2.  人人开放平台API： [http://wiki.dev.renren.com/wiki/V2/user/friend/list](http://wiki.dev.renren.com/wiki/V2/user/friend/list)
3.  淘宝开放平台API： [http://open.taobao.com/api/api_cat_detail.htm?spm=a219a.7386789.0.0.KSaC6l&amp;cat_id=7&amp;category_id=101143](http://open.taobao.com/api/api_cat_detail.htm?spm=a219a.7386789.0.0.KSaC6l&amp;cat_id=7&amp;category_id=101143)
&nbsp;

**从****HTTP****请求和响应格式角度来看：**

基于SOAP协议的Web Service请求和响应格式均是XML

而REST 其请求和响应格式为XML和JSON，现在大部分API设计都使用JSON。

&nbsp;

**Web Service****认证**

1.  以前自己在做REST风格的API时，使用系统随机生成的token string，验证使用服务的第三方传入的token即可。
2.  互联网公司的开放平台一般使用两个key，一个是secret key， 一个是access key。
那我们看下开放平台一般需要两个key，这两个key都是干什么的， 我们看下京东云存储技术文档是怎么描述的：（http://help.jd.com/jos/question-921.html）

**安全认证**

京东云存储会对访问的请求进行安全认证，只有通过认证的请求，才能访问云存储中的数据。

下面是认证的过程：

1.        客户端构造访问云存储的请求

2.        通过 SecretKey 计算请求的签名(Signature)

3.        将附带 AccessKey和签名(Signature)信息的请求发送给京东云存储系统

4.        京东云存储通过请求中的 AccessKey查找对应的 SecretKey

5.        京东云存储利用 SecretKey 重新计算请求的签名(Signature)

6.        若京东云存储计算的签名与客户端提供的签名相匹配，则认证通过，请求被接受，否则京东云存储拒绝处理该请求

京东云存储通过基于 Hmac(Hash Message Authentication Code)算法的自定义 HTTP 头来进行认证操作。要认证一个请求，客户端首先从请求中选取一些关键的元素组成一个字符串(String)，然后利用自己的 SecretKey 计算该字符串的 Hmac 值，这个过程被称之为请求签名（signing the request），计算得出的 Hmac 值被称之为签名（signature），之后，用户将该签名以请求参数的形式发送给京东云存储。

带有认证信息的请求样例：

&nbsp;

DELETE /ccd35eea-3c86-48f4-bd03-2acd5439d12f

Date: Tue, 21 May 2013 10:06:05 GMT

Authorization: jingdong9c379f079214447fad2959c4621cd6feVb797oH1:VREwI/vvZfgds1ueMjy6K0wfqjg=

Host: storage.jcloud.com

&nbsp;

从上面的过程可以发现，又多了个签名的概念。

签名是通过secret key 和 请求中特定的字符串计算出来的，secret key 和access key是一一对应的。

在发送请求时，只需要发送签名和access key即可，服务器端会根据access key 找到对应secret key后再计算一次签名，对比客户端签名和服务器端计算的签名一致性完成认证。

&nbsp;

Secret key更像1个密钥，不可公开。 access key更像这个密钥的标识。有点像SSL中private key 和public key的区别。

&nbsp;

从这个验证流程上来看，第二种认证方式明显比第一种认证方式安全的多，而且可以对第三方调用者进行认证。

&nbsp;

即Web Service服务方可以通过access key确切知道使用第三方服务的用户是谁。这可能就是为什么开放平台一般需要两个key，因为开放平台服务的是大量用户，必须加以区分谁使用了服务。

&nbsp;

**再看看接口设计风格：**

1.  **1.       ****http(s)://domain/path?method=getFriends&amp;param1=value1**
2.  **2.       ****http(s)://domain/path?method=friend.get&amp;param1=value1**
3.  **3.       ****http(s)://domain/path/friend/get?param1=value1**
&nbsp;

以上大概谈了Web Service 是什么、实际应用、数据格式以及安全认证、接口设计，理解还不是很透彻，还有待更深入地研究，特别是在实际使用中去学习了解。
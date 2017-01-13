---
title: Django处理POST请求时，如何设置csrf_token
tags:
  - CSRF
  - Django
  - Mako
  - 模板
id: 742
categories:
  - Django
  - HOWTO
date: 2012-12-06 14:06:43
---

这篇文章主要解决Django应用中post请求时如何设置csrf_token的问题：

1、如何启用Django的csrf_token机制防止csrf攻击？

2、如何在Django自带模板中设置csrf_token？

3、如何在Mako模板中设置csrf_token？

【ENV】

Python :2.7.3

Django :1.4.2

下面一一总结：

**一、如何启用Django的csrf_token机制防止csrf攻击？**

只要在Django 项目的settings.py中添加django.middleware.csrf.CsrfViewMiddleware中间件即可。

如:

[py]
MIDDLEWARE_CLASSES = (
    'django.middleware.common.CommonMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware', #here
    'django.contrib.messages.middleware.MessageMiddleware',
    'djangomako.middleware.MakoMiddleware',
)
[/py]

**二、如何在Django自带模板中设置csrf_token？**

下面主要分为表单提交请求和AJax请求两种情况处理：

不管对于表单请求还是Ajax请求，我们都需要在渲染具有POST请求的模板的View中（render_to_response,该view处理的请求一般为Get请求，主要用来渲染具有POST请求的模板），添加RequestContext，如下：

[py]

def  csrf_post_view(request, template_name)

    return render_to_response（template_name, {}, context_instance=RequestContext(request))

[/py]

然后下面我们在客户端代码对于不同情况作相应处理：

1、普通表单请求

在POST请求的表单中加入csrf_token标记。

[html]

&lt;form  method=&quot;POST&quot; action=&quot;/csrf_test/post_request/&quot;&gt;

{% csrf_token %}

&lt;input type=&quot;text&quot; name=&quot;csrf_test&quot; /&gt;

{#使用csrf_token标记的前提是当前模板使用的是Django默认模板#}  {#这是Django模板的注释语法 #}

&lt;input type=&quot;submit&quot; value=&quot;提交&quot; /&gt;

[/html]

csrf_token标记会在页面上渲染一个隐藏的表单域，如下

[html]
&lt;div style=&quot;display:none&quot;&gt;
&lt;input type=&quot;hidden&quot; value=&quot;effb4e31c9eb7a5817e723124e9e49c1&quot; name=&quot;csrfmiddlewaretoken&quot; /&gt;
&lt;/div&gt;
[/html]

当我们提交表单时，同时csrfmiddlewaretoken也会被提交。

2、Ajax请求

对于Ajax请求，我们可能没有表单，那我们怎么提交csrf_token呢？

同样地，我们在具有POST请求的模板的body标签里放置{% csrf_token %},

此时为了使用Ajax提交该csrf_token，我们需要手动获取构造POST数据，如：

[js]

var url = &quot;/csrf_test/post_request/&quot;;

var csrf_token = jQuery('input[name=csrfmiddlewaretoken').val();

JQuery.post(url, {&quot;csrfmiddlewaretoken&quot;: csrf_token }, function(response){

alert(response);

});

[/js]

如果Ajax请求时，还需要提交表单，我们可以使用jQuery("#formID").serialize()将表单数据转化成一串请求字符串，如csrfmiddlewaretoken=tokenvalue&amp;csrf_test=inputvalue, 然后和其他未在表单范围内的请求字符串连接后一块提交。

**三、如何在Mako模板中设置csrf_token**

Mako模板的具体信息可查看Mako官方文档 http://docs.makotemplates.org/en/latest/

要启用Mako模板机制，需要在settings.py添加中间件djangomako.middleware.MakoMiddleware

views层处理：

[py]

def  csrf_post_view(request, template_name)

    return render_to_response（template_name, {&quot;csrf&quot;:request.COOKIES['csrftoken']})

[/py]

模板层处理：

[html]

&lt;form  method=&quot;POST&quot; action=&quot;/csrf_test/post_request&quot; &gt;

&lt;div style=&quot;display:none&quot;&gt;
&lt;input type=&quot;hidden&quot; name=&quot;csrfmiddlewaretoken&quot; value=&quot;${csrf}&quot; /&gt;
&lt;/div&gt;

&lt;input type=&quot;text&quot; name=&quot;csrf_test&quot; /&gt;

{#使用csrf_token标记的前提是当前模板使用的是Django默认模板#}  {#这是Django模板的注释语法 #}

&lt;input type=&quot;submit&quot; value=&quot;提交&quot; /&gt;

[/html] 
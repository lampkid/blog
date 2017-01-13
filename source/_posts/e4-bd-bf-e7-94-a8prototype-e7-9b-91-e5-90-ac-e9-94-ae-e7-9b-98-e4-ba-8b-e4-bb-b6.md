---
title: 使用prototype监听键盘事件
tags:
  - Javascript
  - prototype
id: 408
categories:
  - HOWTO
  - Javascript
  - prototype
date: 2012-02-20 12:11:55
---

[javascript]
&lt;script&gt;
        Event.observe(document, &quot;keypress&quot;, function(event) {
              //event为一个标准的HTML Event对象
              if (event.keyCode == 13) {
                    alert(e.value);
                }
        });
&lt;/script&gt;
[/javascript]

参考：
[Prototype官网API](http://api.prototypejs.org/dom/Event/)

[http://yuantaosun.blog.sohu.com/78171530.html](http://yuantaosun.blog.sohu.com/78171530.html)
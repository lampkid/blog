---
title: 使用LabVIEW采集声音
tags:
  - LabVIEW
  - 数据采集
id: 547
categories:
  - HOWTO
  - LabVIEW
date: 2012-05-08 08:04:10
---

LabVI EW声音采集程序前面板：

[![声音采集前面板](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E5%A3%B0%E9%9F%B3%E9%87%87%E9%9B%86%E5%89%8D%E9%9D%A2%E6%9D%BF-300x159.jpg "声音采集前面板")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E5%A3%B0%E9%9F%B3%E9%87%87%E9%9B%86%E5%89%8D%E9%9D%A2%E6%9D%BF.jpg)

LabVIEW声音采集程序框图代码：

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E5%A3%B0%E9%9F%B3%E9%87%87%E9%9B%86%E6%A1%86%E5%9B%BE.jpg "声音采集框图")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E5%A3%B0%E9%9F%B3%E9%87%87%E9%9B%86%E6%A1%86%E5%9B%BE.jpg)

下面为采集不同对象声音的结果：

没有任何声音输入，应该是噪声：

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E5%99%AA%E5%A3%B0.jpg "噪声")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E5%99%AA%E5%A3%B0.jpg)

当向麦克风吹气时：

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E5%90%B9%E9%BA%A6%E5%85%8B%E9%A3%8E.jpg "吹麦克风")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E5%90%B9%E9%BA%A6%E5%85%8B%E9%A3%8E.jpg)

当用鼠标不断点击，出现尖峰，尖峰数目与鼠标单击次数相同：

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E9%BC%A0%E6%A0%87%E7%82%B9%E5%87%BB.jpg "鼠标点击")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E9%BC%A0%E6%A0%87%E7%82%B9%E5%87%BB.jpg)

当输入歌曲《 电台情歌》时：

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E7%94%B5%E5%8F%B0%E6%83%85%E6%AD%8C.jpg "电台情歌")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E7%94%B5%E5%8F%B0%E6%83%85%E6%AD%8C.jpg)

当输入歌曲 《飘雪》时：

[![](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E9%A3%98%E9%9B%AA.jpg "飘雪")](http://sunchunman-wordpress.stor.sinaapp.com/uploads/2012/05/%E9%A3%98%E9%9B%AA.jpg)

可以从波形明显看出，音乐的波形为白色，没有一丝红色，而其他均带有红色波形，根据对比猜想，红色波形可能为噪声。
---
title: '使用#Javascript#获得日期'
tags:
  - Date
  - Javascript
  - 日期
id: 192
categories:
  - HOWTO
  - Javascript
date: 2011-12-28 12:54:06
---

Javascript获取日期可以使用Date对象。如果构造函数不带参数，其默认是获取当前日期。

[javascript]
var myDate=new Date();
[/javascript]

举例：
使用Javascript从日期里获取0~23的小时数

[javascript]
&lt;script type=&quot;text/javascript&quot;&gt;// &lt;![CDATA[
//先构造Date对象，可以使用字符串构造Date对象：
var born = new Date(&quot;July 21, 1983 01:15:00&quot;)

//获得日期的小时数使用Date对象的getHours()方法：
document.write(born.getHours())
// ]]&gt;&lt;/script&gt;
[/javascript]

## Date 对象方法

FF: Firefox, IE: Internet Explorer
<table width="650">
<tbody>
<tr>
<th>方法</th>
<th>描述</th>
</tr>
<tr>
<td>[Date()](/js/jsref_Date.asp)</td>
<td>返回当日的日期和时间。</td>
</tr>
<tr>
<td>[getDate()](/js/jsref_getDate.asp)</td>
<td>从 Date 对象返回一个月中的某一天 (1 ~ 31)。</td>
</tr>
<tr>
<td>[getDay()](/js/jsref_getDay.asp)</td>
<td>从 Date 对象返回一周中的某一天 (0 ~ 6)。</td>
</tr>
<tr>
<td>[getMonth()](/js/jsref_getMonth.asp)</td>
<td>从 Date 对象返回月份 (0 ~ 11)。</td>
</tr>
<tr>
<td>[getFullYear()](/js/jsref_getFullYear.asp)</td>
<td>从 Date 对象以四位数字返回年份。</td>
</tr>
<tr>
<td>[getYear()](/js/jsref_getYear.asp)</td>
<td>请使用 getFullYear() 方法代替。</td>
</tr>
<tr>
<td>[getHours()](/js/jsref_getHours.asp)</td>
<td>返回 Date 对象的小时 (0 ~ 23)。</td>
</tr>
<tr>
<td>[getMinutes()](/js/jsref_getMinutes.asp)</td>
<td>返回 Date 对象的分钟 (0 ~ 59)。</td>
</tr>
<tr>
<td>[getSeconds()](/js/jsref_getSeconds.asp)</td>
<td>返回 Date 对象的秒数 (0 ~ 59)。</td>
</tr>
<tr>
<td>[getMilliseconds()](/js/jsref_getMilliseconds.asp)</td>
<td>返回 Date 对象的毫秒(0 ~ 999)。</td>
</tr>
<tr>
<td>[getTime()](/js/jsref_getTime.asp)</td>
<td>返回 1970 年 1 月 1 日至今的毫秒数。</td>
</tr>
<tr>
<td>[getTimezoneOffset()](/js/jsref_getTimezoneOffset.asp)</td>
<td>返回本地时间与格林威治标准时间 (GMT) 的分钟差。</td>
</tr>
<tr>
<td>[getUTCDate()](/js/jsref_getUTCDate.asp)</td>
<td>根据世界时从 Date 对象返回月中的一天 (1 ~ 31)。</td>
</tr>
<tr>
<td>[getUTCDay()](/js/jsref_getUTCDay.asp)</td>
<td>根据世界时从 Date 对象返回周中的一天 (0 ~ 6)。</td>
</tr>
<tr>
<td>[getUTCMonth()](/js/jsref_getUTCMonth.asp)</td>
<td>根据世界时从 Date 对象返回月份 (0 ~ 11)。</td>
</tr>
<tr>
<td>[getUTCFullYear()](/js/jsref_getUTCFullYear.asp)</td>
<td>根据世界时从 Date 对象返回四位数的年份。</td>
</tr>
<tr>
<td>[getUTCHours()](/js/jsref_getUTCHours.asp)</td>
<td>根据世界时返回 Date 对象的小时 (0 ~ 23)。</td>
</tr>
<tr>
<td>[getUTCMinutes()](/js/jsref_getUTCMinutes.asp)</td>
<td>根据世界时返回 Date 对象的分钟 (0 ~ 59)。</td>
</tr>
<tr>
<td>[getUTCSeconds()](/js/jsref_getUTCSeconds.asp)</td>
<td>根据世界时返回 Date 对象的秒钟 (0 ~ 59)。</td>
</tr>
<tr>
<td>[getUTCMilliseconds()](/js/jsref_getUTCMilliseconds.asp)</td>
<td>根据世界时返回 Date 对象的毫秒(0 ~ 999)。</td>
</tr>
<tr>
<td>[parse()](/js/jsref_parse.asp)</td>
<td>返回1970年1月1日午夜到指定日期（字符串）的毫秒数。</td>
</tr>
<tr>
<td>[setDate()](/js/jsref_setDate.asp)</td>
<td>设置 Date 对象中月的某一天 (1 ~ 31)。</td>
</tr>
<tr>
<td>[setMonth()](/js/jsref_setMonth.asp)</td>
<td>设置 Date 对象中月份 (0 ~ 11)。</td>
</tr>
<tr>
<td>[setFullYear()](/js/jsref_setFullYear.asp)</td>
<td>设置 Date 对象中的年份（四位数字）。</td>
</tr>
<tr>
<td>[setYear()](/js/jsref_setYear.asp)</td>
<td>请使用 setFullYear() 方法代替。</td>
</tr>
<tr>
<td>[setHours()](/js/jsref_setHours.asp)</td>
<td>设置 Date 对象中的小时 (0 ~ 23)。</td>
</tr>
<tr>
<td>[setMinutes()](/js/jsref_setMinutes.asp)</td>
<td>设置 Date 对象中的分钟 (0 ~ 59)。</td>
</tr>
<tr>
<td>[setSeconds()](/js/jsref_setSeconds.asp)</td>
<td>设置 Date 对象中的秒钟 (0 ~ 59)。</td>
</tr>
<tr>
<td>[setMilliseconds()](/js/jsref_setMilliseconds.asp)</td>
<td>设置 Date 对象中的毫秒 (0 ~ 999)。</td>
</tr>
<tr>
<td>[setTime()](/js/jsref_setTime.asp)</td>
<td>以毫秒设置 Date 对象。</td>
</tr>
<tr>
<td>[setUTCDate()](/js/jsref_setUTCDate.asp)</td>
<td>根据世界时设置 Date 对象中月份的一天 (1 ~ 31)。</td>
</tr>
<tr>
<td>[setUTCMonth()](/js/jsref_setUTCMonth.asp)</td>
<td>根据世界时设置 Date 对象中的月份 (0 ~ 11)。</td>
</tr>
<tr>
<td>[setUTCFullYear()](/js/jsref_setUTCFullYear.asp)</td>
<td>根据世界时设置 Date 对象中的年份（四位数字）。</td>
</tr>
<tr>
<td>[setUTCHours()](/js/jsref_setutchours.asp)</td>
<td>根据世界时设置 Date 对象中的小时 (0 ~ 23)。</td>
</tr>
<tr>
<td>[setUTCMinutes()](/js/jsref_setUTCMinutes.asp)</td>
<td>根据世界时设置 Date 对象中的分钟 (0 ~ 59)。</td>
</tr>
<tr>
<td>[setUTCSeconds()](/js/jsref_setUTCSeconds.asp)</td>
<td>根据世界时设置 Date 对象中的秒钟 (0 ~ 59)。</td>
</tr>
<tr>
<td>[setUTCMilliseconds()](/js/jsref_setUTCMilliseconds.asp)</td>
<td>根据世界时设置 Date 对象中的毫秒 (0 ~ 999)。</td>
</tr>
<tr>
<td>[toSource()](/js/jsref_tosource_boolean.asp)</td>
<td>返回该对象的源代码。</td>
</tr>
<tr>
<td>[toString()](/js/jsref_toString_date.asp)</td>
<td>把 Date 对象转换为字符串。</td>
</tr>
<tr>
<td>[toTimeString()](/js/jsref_toTimeString.asp)</td>
<td>把 Date 对象的时间部分转换为字符串。</td>
</tr>
<tr>
<td>[toDateString()](/js/jsref_toDateString.asp)</td>
<td>把 Date 对象的日期部分转换为字符串。</td>
</tr>
<tr>
<td>[toGMTString()](/js/jsref_toGMTString.asp)</td>
<td>请使用 toUTCString() 方法代替。</td>
</tr>
<tr>
<td>[toUTCString()](/js/jsref_toUTCString.asp)</td>
<td>根据世界时，把 Date 对象转换为字符串。</td>
</tr>
<tr>
<td>[toLocaleString()](/js/jsref_toLocaleString.asp)</td>
<td>根据本地时间格式，把 Date 对象转换为字符串。</td>
</tr>
<tr>
<td>[toLocaleTimeString()](/js/jsref_toLocaleTimeString.asp)</td>
<td>根据本地时间格式，把 Date 对象的时间部分转换为字符串。</td>
</tr>
<tr>
<td>[toLocaleDateString()](/js/jsref_toLocaleDateString.asp)</td>
<td>根据本地时间格式，把 Date 对象的日期部分转换为字符串。</td>
</tr>
<tr>
<td>[UTC()](/js/jsref_utc.asp)</td>
<td>根据世界时返回 1970 年 1 月 1 日 到指定日期的毫秒数。</td>
</tr>
<tr>
<td>[valueOf()](/js/jsref_valueOf_date.asp)</td>
<td>返回 Date 对象的原始值。</td>
</tr>
</tbody>
</table>
参考：
[w3school](http://www.w3school.com.cn/js/jsref_getHours.asp)
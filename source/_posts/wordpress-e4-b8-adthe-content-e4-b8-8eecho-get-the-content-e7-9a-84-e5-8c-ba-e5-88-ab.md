---
title: wordpress中the_content()与echo get_the_content()的区别
id: 576
categories:
  - HOWTO
  - wordpress
date: 2012-05-19 14:55:26
tags:
---

2012年5月19日， 帮师兄做一个企业网站时发现这么一个现象：

the_content() 输出时不会过滤掉文章格式中的段落标签 &lt;p&gt;,

而echo get_the_content()输出时，会过滤掉文章格式中的段落标签 &lt;p&gt;。

对其百思不得其解，只能在源码中寻个究竟，the_content()和get_the_content()均在wp-includes/post-template.php中，而且the_content()调用了get_the_content()。我们来看源代码：

[code]

/**
* Display the post content.
*
* @since 0.71
*
* @param string $more_link_text Optional. Content for when there is more text.
* @param string $stripteaser Optional. Teaser content before the more text.
*/
function the_content($more_link_text = null, $stripteaser = 0) {
$content = get_the_content($more_link_text, $stripteaser);
$content = apply_filters('the_content', $content);
$content = str_replace(']]&gt;', ']]&amp;gt;', $content);
echo $content;
}

/**
* Retrieve the post content.
*
* @since 0.71
*
* @param string $more_link_text Optional. Content for when there is more text.
* @param string $stripteaser Optional. Teaser content before the more text.
* @return string
*/
function get_the_content($more_link_text = null, $stripteaser = 0) {
global $post, $more, $page, $pages, $multipage, $preview;

if ( null === $more_link_text )
$more_link_text = __( '(more...)' );

$output = '';
$hasTeaser = false;

// If post password required and it doesn't match the cookie.
if ( post_password_required($post) ) {
$output = get_the_password_form();
return $output;
}

if ( $page &gt; count($pages) ) // if the requested page doesn't exist
$page = count($pages); // give them the highest numbered page that DOES exist

$content = $pages[$page-1];
if ( preg_match('/&lt;!--more(.*?)?--&gt;/', $content, $matches) ) {
$content = explode($matches[0], $content, 2);
if ( !empty($matches[1]) &amp;&amp; !empty($more_link_text) )
$more_link_text = strip_tags(wp_kses_no_null(trim($matches[1])));

$hasTeaser = true;
} else {
$content = array($content);
}
if ( (false !== strpos($post-&gt;post_content, '&lt;!--noteaser--&gt;') &amp;&amp; ((!$multipage) || ($page==1))) )
$stripteaser = 1;
$teaser = $content[0];
if ( ($more) &amp;&amp; ($stripteaser) &amp;&amp; ($hasTeaser) )
$teaser = '';
$output .= $teaser;
if ( count($content) &gt; 1 ) {
if ( $more ) {
$output .= '&lt;span id=&quot;more-' . $post-&gt;ID . '&quot;&gt;&lt;/span&gt;' . $content[1];
} else {
if ( ! empty($more_link_text) )
$output .= apply_filters( 'the_content_more_link', ' &lt;a href=&quot;' . get_permalink() . &quot;#more-{$post-&gt;ID}\&quot; class=\&quot;more-link\&quot;&gt;$more_link_text&lt;/a&gt;&quot;, $more_link_text );
$output = force_balance_tags($output);
}

}
if ( $preview ) // preview fix for javascript bug with foreign languages
$output =    preg_replace_callback('/\%u([0-9A-F]{4})/', '_convert_urlencoded_to_entities', $output);

return $output;
}

[/code]

我们可以发现the_content()使用get_the_content()获得文章内容后，使用下面几行代码对文章内容做了处理：

[code]

$content = apply_filters('the_content', $content);
$content = str_replace(']]&gt;', ']]&amp;gt;', $content);
echo $content;

[/code]

wordpress会先执行挂在钩子the_content上的所有函数（过滤器），然后使用str_replace将文章内容中的]]&gt;替换为]]&amp;gt;，然后返回处理后的文章内容。

还是看不出问题原因。经过测试，原因出现在[code] $content = apply_filters('the_content', $content);[/code]

,一定是执行了什么钩子函数，才恢复了文章本来的格式。

那到底执行了什么钩子函数呢？ 苦心寻找，未果。

&nbsp;
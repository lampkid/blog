---
title: Django部署admin和Flatpages应用
tags:
  - CMS
  - Django
  - Flatpages
id: 717
categories:
  - Django
  - HOWTO
date: 2012-11-26 08:18:42
---

【ENV】
Python版本：2.7.3
Django版本：1.4
数据库：SQLite3
操作系统：Linux 3.5.7-gentoo

【部署步骤】
1、安装python2.7
[bash]
emerge -v python:2.7
[/bash]
注意，直接emerge python,会安装为python3。

如果系统安装有多个python版本，请设置默认python为2.7
[python]
eselect python list
eselect python set 1
[/python]

2、安装Django
  1）可使用emerge django 命令安装
  2）或将django源码包下载下来，解压到python安装路径的site-packages/目录下，但需要设置django-admin.py的环境变量

3、安装sqlite
[bash]
   emerge sqlite
[/bash]
4、安装pysqlite
   pysqlite是SQLite的python驱动接口，如果未安装，将无法操作数据库。
 [bash]
emerge pysqlite
[/bash]

5、创建django项目cms
 [bash]
 django-admin.py startproject cms
 [/bash]

6、配置参数文件settings.py
  1）数据库设置
[python]
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3', # Add 'postgresql_psycopg2', 'mysql', 'sqlite3' or 'oracle'.
        'NAME': 'cms.db',                      # Or path to database file if using sqlite3.
        'USER': '',                      # Not used with sqlite3.
        'PASSWORD': '',                  # Not used with sqlite3.
        'HOST': '',                      # Set to empty string for localhost. Not used with sqlite3.
        'PORT': '',                      # Set to empty string for default. Not used with sqlite3.
    }
}
[/python]

  2）添加admin和flatpages应用
   [python]
    INSTALLED_APPS = (
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.sites',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    # Uncomment the next line to enable the admin:
    'django.contrib.flatpages',
    'django.contrib.admin', 
    # Uncomment the next line to enable admin documentation:
    # 'django.contrib.admindocs',
)
   [/python]

  3) Flatpages中间件设置
     如果Flatpages应用发生404页面，由该中间件处理；
     [python]
    MIDDLEWARE_CLASSES = (
    'django.middleware.common.CommonMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.contrib.flatpages.middleware.FlatpageFallbackMiddleware',
    # Uncomment the next line for simple clickjacking protection:
    # 'django.middleware.clickjacking.XFrameOptionsMiddleware',
)
     [/python]
 4)模板目录配置
  将模板文件存放目录设置为应用根目录下的templates目录
  [python]
   TEMPLATE_DIRS = (
    # Put strings here, like &quot;/home/html/django_templates&quot; or &quot;C:/www/django/templates&quot;.
    # Always use forward slashes, even on Windows.
    # Don't forget to use absolute paths, not relative paths.
    os.path.join(os.path.dirname(__file__), 'templates').replace('\\','/'),
)
   [/python]
设置完模板目录后，在cms应用下创建templates/flatpages/目录，并创建模板文件default.html,
即cms/cms/templates/flatpages/default.html,
[html]
&lt;html&gt;
    &lt;head&gt;
        &lt;title&gt;{{flatpage.title}}&lt;/title&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;h1&gt;{{flatpage.title}}&lt;/h1&gt;
        &lt;div&gt;{{flatpage.content}}&lt;/div&gt;
    &lt;/body&gt;
&lt;/html&gt;
[/html]

  5）路由配置（url）
   编辑cms/cms下的urls.py,配置url路由，注意去掉admin.autodiscover()的注释。
[python]
from django.conf.urls import patterns, include, url

# Uncomment the next two lines to enable the admin:
from django.contrib import admin
admin.autodiscover()

urlpatterns = patterns('',
    # Examples:
    # url(r'^$', 'cms.views.home', name='home'),
    # url(r'^cms/', include('cms.foo.urls')),

    # Uncomment the admin/doc line below to enable admin documentation:
    # url(r'^admin/doc/', include('django.contrib.admindocs.urls')),

    # Uncomment the next line to enable the admin:
    url(r'^admin/', include(admin.site.urls)),
    url(r'^pages/', include('django.contrib.flatpages.urls')),
)
[/python]

   6）创建数据库，同步数据库；
[bash]
python manage.py syncdb
[/bash] 
此时会让创建管理员，根据提示创建，后面登录时会用到，一定要remember。
   7）运行起我们的django应用
     python manage.py runserver 0:60000

在浏览器里输入http://ip:60000,即可看到登录界面，使用刚才创建数据库时创建的用户名和密码登录，并继续操作其他页面。
---
title: 'HOWTO:Django自定义manage.py Commands'
tags:
  - Django
  - Python
id: 651
categories:
  - Django
  - HOWTO
date: 2012-10-15 08:41:30
---

manage.py 是Django项目内置的一个命令，可用manage.py启动Django内置web服务器，如[bash] python manage.py runserver 0:60000[/bash]

, runserver命令即为Django内置的一个manage.py命令。其他命令可用[bash] python manage.py --help[/bash]

查找。

Django内置命令都存储在django.core.management.commands包下，如何自定义Commands呢？其实很简单，只需要在一个Python文件里定义一个Command类即可。
如在custom_command.py定义一个Command类：
[py]
# -*- coding:utf-8 -*-
from django.core.management.base import BaseCommand, CommandError
class Command(BaseCommand):

    help = 'python manage.py custom_command'

    def handle(self, **options):
        print &quot;hello, I am a custom command&quot;
[/py]

定义好Command类后，我们还不能用manage.py执行自定义的命令，还需要将custom_command.py文件放在特定的目录里：
方法一：
将custom_command.py直接放在django.core.management.commands包下即可。
方法二：
在Django项目的任意一个app里创建management.commands包，然后将自定义命令的类文件custom_command.py放在management.commands下即可。
方法三：
1、在PYTHONPATH里任意新建一个目录，如customs； 
2、将自定义命令的类文件custom_command.py放在customs.management.commands里；
3、修改django.core.management下的__init__.py里的函数get_commands()函数：
  [py]
def get_commands():
    global _commands
    if _commands is None:
        print __path__, 'path'
        _commands = dict([(name, 'django.core') for name in find_commands(__path__[0])])      

        # Find the installed apps                                                             
        try:
            from django.conf import settings                                                  
            apps = settings.INSTALLED_APPS
        except (AttributeError, EnvironmentError, ImportError):                               
            apps = []                                                                         

        # Find and load the management module for each installed app.
        for app_name in apps:
            try:
                path = find_management_module(app_name)
                _commands.update(dict([(name, app_name)
                                       for name in find_commands(path)]))
            except ImportError:
                pass # No management module - ignore this app
    # 加入下面一行：
    _commands.update(dict([(name, 'customs')
                           for name in find_commands('/python_path_dir/customs/management')]))
    return _commands
  [/py] 
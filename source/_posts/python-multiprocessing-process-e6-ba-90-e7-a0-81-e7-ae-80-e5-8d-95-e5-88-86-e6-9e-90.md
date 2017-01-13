---
title: Python multiprocessing.Process源码简单分析
tags:
  - multiprocessing
  - Python
  - 进程
id: 725
categories:
  - Python
  - 猿说技术
date: 2012-12-02 06:47:41
---

在Python的multiprocessing模块中，提供了创建进程、进程池、队列、堆分配、同步、信号等功能。这里，我们将重点放在进程创建、进程池以及队列上。

首先从一个小问题开始：
下面的代码将创建一个进程，让其运行特定的函数：
【code-1】
[python]
#!/usr/bin/env python
#-*.*-coding:utf8-*.*-

from multiprocessing.self_process import Process

def target_func():
    print 'target_func'

if __name__ == '__main__':
    p=Process(target=target_func, name='process_start_test')
    p.start()
    p.join()
[/python]
上面的代码可正常运行退出。

如果我们稍微添加这么一句，又会是怎样的情况呢？请看下面的代码：
【code-2】
[python]
#!/usr/bin/env python
#-*.*-coding:utf8-*.*-

from multiprocessing.self_process import Process

def target_func():
    print 'target_func'

if __name__ == '__main__':
    p=Process(target=target_func, name='process_start_test')
    p.start()
    p.start() #看见了吧，我们对该进程p启动了两次
    p.join()
[/python]
此段代码运行后异常退出：
【result-2】
[python]
Traceback (most recent call last):
  File &quot;process_start.py&quot;, line 15, in &lt;module&gt;
    p.start()
  File &quot;/usr/lib/python2.7/multiprocessing/process.py&quot;, line 120, in start
    assert self._popen is None, 'cannot start a process twice'
AssertionError: cannot start a process twice
target_func
[/python]
从结果中，我们可以看到，有一个p.start()确实成功运行，但当第二次启动该进程时，报出AssertionError异常。
该异常出自哪段代码呢？让我们看看multiprocessing.Process start方法的源码：
【code-3】
[python]
 def start(self):
        '''
        Start child process
        '''
        assert self._popen is None, 'cannot start a process twice'
        assert self._parent_pid == os.getpid(), \
               'can only start a process object created by current process'
        assert not _current_process._daemonic, \
               'daemonic processes are not allowed to have children'
        _cleanup()
        if self._Popen is not None:
            Popen = self._Popen
        else:
            from .forking import Popen
        self._popen = Popen(self)
        _current_process._children.add(self)

[/python]
在Process.start()方法中，我们注意到下面这行代码
【code-4】
[python]
        assert self._popen is None, 'cannot start a process twice'
[/python]
异常就是从此爆出。
当我们p.start()第二次时，此时self._popen已经不是None了，所以assert self._popen is None已不再成立，从而爆出AssertionError异常。

那么如何避免多次调用p.start()方法时爆出此异常呢？
很简单，注释掉multiprocessing/process.py中的assert语句（即code-4,上面的Process.start()方法中的assert）
然后我们再运行code-2,此次可正常运行，如我们所愿，**但是**：

我们为什么要修改Python本身的代码呢？
我么可以在multiprocessing包中做一个process.py的拷贝，如self_process.py,引用的时候可以采用下面的方法：
【code-5】
[python]
#!/usr/bin/env python
#-*.*-coding:utf8-*.*-

def target_func():
    print 'target_func'

if __name__ == '__main__':
    from multiprocessing import self_process
    p=self_process.Process(target=target_func, name='process_start_test')
    p.start()
    p.start() #看见了吧，我们对该进程p启动了两次
    p.join()
[/python]
这样就避免了对Python本身Process的修改。

**但是：**
我们运行下面的代码：
【code-6】
[python]
def target_func():
    from time import sleep
    sleep(5)
    print 'target_func'

if __name__ == '__main__':
    from multiprocessing import self_process
    p=self_process.Process(target=target_func, name='process_start')
    p.start()
    p.start()
    p.join()
[/python]

当我们再shell终端查看process_start进程时，可以看到同时有两个进程在运行，也就是说我们只要start一次，就会fork出一个新进程。
[bash]
ps aux|grep process_start

root      2344  4.0  0.7   7144  3940 pts/2    S+   20:12   0:00 /usr/bin/python2.7 process_start.py
root      2345  0.0  0.4   7144  2556 pts/2    S+   20:12   0:00 /usr/bin/python2.7 process_start.py
root      2346  0.0  0.4   7144  2564 pts/2    S+   20:12   0:00 /usr/bin/python2.7 process_start.py
root      2348  0.0  0.1   3912   792 pts/1    S+   20:12   0:00 grep --colour=auto process_start

[/bash]
为什么会这样呢?
从Process的start方法中可以看出start运行的逻辑：
Process.start()方法会调用forking模块的Popen创建一个新进程。

让我们看看Popen类的源码（在multiprocessing/forking.py）
【code-7】
[python]
class Popen(object):

        def __init__(self, process_obj):
            sys.stdout.flush()
            sys.stderr.flush()
            self.returncode = None

            self.pid = os.fork()
            if self.pid == 0:
                if 'random' in sys.modules:
                    import random
                    random.seed()
                code = process_obj._bootstrap()
                sys.stdout.flush()
                sys.stderr.flush()
                os._exit(code)

[/python]
在Popen初始化__init__中，可以看到os.fork的调用，fork方法会创建一个父进程的拷贝作为子进程，当我们在终端运行
python process_start.py时，已经创建了一个进程即python process_start.py，所以我们在ps aux中看到的不只两次p.start()后fork的进程，而是看到了包括python process_start.py时本身在内的三个python process_start.py进程。

这可能就是Python不让一个Process start两次的原因吧。
到这，我们还要提及一点，即Process还有一个run方法，无论我们调用多少次run方法都不会报出不能run两次的异常，因为run方法根本就没有创建子进程，而是在进程本身空间内执行了一个普通的方法而已，而且run方法是同步阻塞的，而start方法是通过Popen  fork出的子进程启动的run方法，所以start方法可以做到异步。

**启动进程前重新指定进程执行的目标函数：**
【code-8】
[python]
def target_func1():
    from time import sleep
    sleep(5)
    print 'target_func1'

def target_func2():
    from time import sleep
    sleep(5)
    print 'target_func2'

if __name__ == '__main__':
    from multiprocessing import self_process
    p=self_process.Process(target=target_func, name='process_start')
    p.start()
    p._target = target_func2
    p.start()
    p.join()
[/python]

我们再来看一个新话题，进程池：
在multiprocessing包中已经实现了进程池，
【code-9】
[python]
#!/usr/bin/env python
#-*.*-coding:utf8-*.*-

def init_func():
    print 'pool init_func'

def target_func():
    from time import sleep
    sleep(1)
    print 'target_func'

if __name__ == '__main__':
    from multiprocessing import Pool
    pool_size = 4
    pool = Pool(processes=pool_size,initializer=init_func, maxtasksperchild=2)
    a=pool.apply_async(target_func)
    pool.close()
    pool.join()

[/python]
python multiprocessing.Pool实现的进程池有以下我们需要注意的特点：
1、使用队列实现；multiprocessing.Queue
2、当进程池里的进程小于我们初始化的进程池大小时，Pool会创建新的Process并加入进程池Queue中。

所以我们实现自己的进程池时，我们可以避免AssertionError异常，但我们发现，Process.start()方法还会创建新进程，我们只是省略了创建Process自身的过程，但在Process.start()时，Process还会通过Popen fork一个子进程。
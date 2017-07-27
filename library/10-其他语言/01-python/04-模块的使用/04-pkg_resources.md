### pkg_resources
http://www.cnblogs.com/babykick/archive/2012/03/09/2387808.html
#### load_entry_point
```python
import sys
from pkg_resources import load_entry_point
sys.exit(
   load_entry_point('supervisor==3.1.3', 'console_scripts', 'supervisord')()
)
#  load_entry_point 定义了script的一个框架，当安装新的包的时候，只要setup.py指定好entry_points，指明从哪里开始调用函数或者模块(上面举了distutils.commands例子)，然后 load_entry_point或者run_script就可以了。这样做的好处是将调用和具体实现分离开
# 第一个参数,supervisor==3.1.3, 可以定向到/usr/local/lib/python2.7/site-packages/supervisor-3.1.3-py2.7.egg-info，搜索entry_points.txt
"""
[console_scripts]
echo_supervisord_conf = supervisor.confecho:main
pidproxy = supervisor.pidproxy:main
supervisorctl = supervisor.supervisorctl:main
supervisord = supervisor.supervisord:main
"""
# 上面是entry_points.txt的定义，console_scripts,就是第二个参数，第三个参数对应配置中的 supervisord, 指向 supervisor模块下的supervisord文件中的main函数，调用执行
```

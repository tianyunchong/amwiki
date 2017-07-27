### supervisor命令行启动解析
#### 启动命令
```shell
/usr/local/bin/python /usr/bin/supervisord -c /etc/supervisord.conf
```
#### 启动命令文件
```python
#vim /usr/bin/supervisord
__requires__ = 'supervisor==3.1.3'
import sys  
from pkg_resources import load_entry_point

sys.exit(   
   load_entry_point('supervisor==3.1.3', 'console_scripts', 'supervisord')()
)
# load_entry_point库查找到程序/usr/local/lib/python2.7/site-packages/supervisor/supervisord.py执行main函数
```

#### 测试解析执行命令
```python
from supervisor.options import ServerOptions
from supervisor.supervisord import Supervisor
# 开始接收参数，读取配置文件，获取配置数据处理
options = ServerOptions()
options.realize(None, doc=__doc__)
# options相关参数
print options.parse_infos #输出解析信息
print options.parse_warnings #输出解析警告信息
```

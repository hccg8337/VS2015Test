# testhost使用说明
**testhost v1.1**是基于rpyc开发一套远程调用执行接口。

1. **简单示例**
```
#!/usr/bin/env python
# coding=utf-8
import rpyc
import threading
import time
c = rpyc.connect('10.66.81.117', '11111')
result = c.root.exposed_popen_sync(r'run.bat')
print(result[1][0].decode('gbk'))
print(result[1][1].decode('gbk'))
c.close()
```
2. **详细接口**
| 接口 |          接口参数           |  说明  |
|--|-----------------------|--|
|  exposed_del_console  | None |   删除console日志   |
|  exposed_console  |      tell: 读取位置(str/int)      |   获取日志   |
|  exposed_popen_async  |        cmd: 命令(str)        |   异步执行命令   |
| exposed_returncode  |        None        |   获取异步执行返回码，未执行完返回None   |
|  exposed_terminate  |        None        |   终止本次执行   |
| exposed_warn_terminate  |      pid: 进程id      |   终止指定进程id   |
| exposed_module_func  |  module_name: 模块名称, func: 方法名称, \*args, \*\*kwargs 方法参数  |   动态加载模块，执行模块函数   |

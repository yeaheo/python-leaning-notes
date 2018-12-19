# sys 模块

sys 模块一般用的不是很多，这里简单介绍几个方法，如果有需要后期也会更新，毕竟活到老学到老嘛。

各种方法的时候可以参考下面的描述信息：

**sys.argv**           

该方法相当于命令行参数``List``，第一个元素是程序本身路径：

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

import sys
print(sys.argv)

# 程序执行结果
['/Users/qingclass/workspace/mypy/modules/sys-module.py']
```

**sys.exit(n)**        

该方法用于退出程序，正常退出时exit(``0``)：

```python
import sys
sys.exit(0)
```

**sys.version**        

该方法用于获取 Python 解释程序的版本信息：

```python
import sys
print(sys.version)

# 程序执行结果
3.7.1 (v3.7.1:260ec2c36a, Oct 20 2018, 03:13:28) 
[Clang 6.0 (clang-600.0.57)]
```

**sys.path**           

该方法用于返回模块的搜索路径，初始化时使用 PYTHONPATH 环境变量的值

```python
import sys
print(sys.path)

# 程序执行结果
['/Users/qingclass/workspace/mypy/modules', '/Users/qingclass/workspace/mypy/modules', '/Library/Frameworks/Python.framework/Versions/3.7/lib/python37.zip',....
```

**sys.platform**       

该方法用于返回操作系统平台名称：

```python
import sys
print(sys.platform)

# 程序执行结果
darwin
```

### 利用 sys 模块的实例

```python
import sys,time
for i in range(10):
    sys.stdout.write('#')
    time.sleep(1)
    sys.stdout.flush()
    
# 程序执行结果
##########
```


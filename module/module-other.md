# 其他模块

我们常用的模块其实还有几个，包括 hashlib 

### hashlib 模块

用于加密相关的操作，3.x 版本里代替了 md5 模块和 sha 模块，主要提供 SHA1, SHA224, SHA256, SHA384, SHA512,MD5 算法

示例代码：

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

import hashlib

obj = hashlib.md5("eric".encode("utf-8"))  # 加盐
obj.update("hello".encode("utf-8"))        # MD5 加密
print(obj.hexdigest())                     # 输出 MD5 值

obj.update("admin".encode("utf-8"))        # 这个是在上面的基础上做的 MD5 ，相当于 helloadmin  
print(obj.hexdigest())

# 程序执行结果
19062eeafd7f9ed4ae2c59c9335e4443
111067c5e558a2fe301e40e1d0e58fb3

=========================================
import hashlib
obj.update("helloadmin".encode("utf-8"))
print(obj.hexdigest())

# 程序执行结果
111067c5e558a2fe301e40e1d0e58fb3   #（MD5值唯一）
```




# time 模块

一般在 Python 中有三种表示时间的形式，分别为结构化时间(struct_time)、字符串时间(string_time)和时间戳(timestamp)。这三种时间形式具体描述如下：

- 结构化时间（struct_time）：结构化时间一般是一种元组的表现形式，struct_time 元组共有9个元素共九个元素:(年，月，日，时，分，秒，一年中第几周，一年中第几天，夏令时)。
- 字符串时间（string_time）：字符串时间就是通常我们所见到的类似 `2018-12-22`的表现形式。
- 时间戳（timestamp）：时间戳表示的是从1970年1月1日00:00:00开始按秒计算的偏移量。我们运行 `type(time.time())`，返回的是float类型.

下面几个小示例分别展示了这几种时间的表现形式：

**时间戳**

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

import time
print(time.time())

# 程序输出结果
1545051895.6365447    # 该单位为秒，表示距离1970-1-1 00:00:00开始的偏移量
```

**结构化时间**

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

import time

print(time.localtime())
t = time.localtime()
print(t.tm_year)

# 程序执行结果
time.struct_time(tm_year=2018, tm_mon=12, tm_mday=17, tm_hour=21, tm_min=7, tm_sec=42, tm_wday=0, tm_yday=351, tm_isdst=0)
2018
```

**字符串时间**

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

import time


print(time.strftime("%Y-%m-%d %X",time.localtime()))
print(time.strftime("%Y-%m-%d %H:%M:%S",time.localtime()))

# 程序执行结果
2018-12-17 21:11:15
2018-12-17 21:11:15
```




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

print(time.localtime()) # time.localtime()没有参数时表示的是当前时间，也可以自定义时间戳参数
t = time.localtime()
print(t.tm_year)

# 程序执行结果
time.struct_time(tm_year=2018, tm_mon=12, tm_mday=17, tm_hour=21, tm_min=7, tm_sec=42, tm_wday=0, tm_yday=351, tm_isdst=0)
# 年月日时分秒，一年中的第几周，一年中的第几天，夏令时
2018
```

结构化时间方法常用的还用一个是 `gtime()`该方法和 `localtime()`方法类似，表示的也是结构化时间，不同的是该方法表示的是UTC时间的结构化时间：

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

import time

print(time.gmtime())

# 程序执行结果
time.struct_time(tm_year=2018, tm_mon=12, tm_mday=18, tm_hour=12, tm_min=59, tm_sec=5, tm_wday=1, tm_yday=352, tm_isdst=0)
```

字符串时间**

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

**三种时间形式的相互转换**

结构化时间和时间戳形式的时间可以相互转化，结构化时间和字符串时间也可以相互转化，但是字符串时间和时间戳时间不能相互转化，具体的转化关系可以参考下图：

![三种时间形式的转换关系](https://ws1.sinaimg.cn/large/006tNbRwly1fyb7971q61j30oc0da0vh.jpg)

下面用具体的实例表示这三者之间的转换关系：

**1、时间戳时间转换为结构化时间**

```python
import time

# 时间戳转换为结构化时间
test_a = time.localtime(time.time()) # 当前时区
test_b = time.gmtime(time.time())  # UTC时间
print(test_a)
print(test_b)

# 程序执行结果
time.struct_time(tm_year=2018, tm_mon=12, tm_mday=18, tm_hour=21, tm_min=10, tm_sec=8, tm_wday=1, tm_yday=352, tm_isdst=0)
time.struct_time(tm_year=2018, tm_mon=12, tm_mday=18, tm_hour=13, tm_min=11, tm_sec=9, tm_wday=1, tm_yday=352, tm_isdst=0)
```

**2、结构化时间转化为时间戳时间**

```python
import time

# 结构化时间转换成时间戳
a = time.mktime(time.localtime())
print(a)

# 程序执行结果
1545138669.0
```

**3、结构化时间转换为字符串时间**

```python
# asctime([t]) : 把一个表示时间的元组或者struct_time表示为这种形式：'Sun Jun 20 23:21:05 1993'这其实也是一种字符串表现形式，如果没有参数，将会将time.localtime()作为参数传入

import time
test_d = time.asctime(time.localtime())
print(test_d)

# 程序执行结果
Tue Dec 18 21:20:25 2018
```

```python
# strftime(format[, t]) : 把一个代表时间的元组或者struct_time（如由time.localtime()和time.gmtime()转化为格式化的时间字符串。如果t未指定，将传入time.localtime()。如果元组中任何一个元素越界，ValueError的错误将会被抛出。

import time
test_e = time.strftime("%Y-%m-%d %X",time.localtime())
test_f = time.strftime("%Y-%m-%d %H:%M:%S",time.localtime())
print(test_e)
print(test_f)

# 程序执行结果
2018-12-18 21:26:50
2018-12-18 21:26:50
```

**4、字符串时间转换为结构化时间**

```python
# time.strptime(string[, format])把一个格式化时间字符串转化为struct_time。实际上它和strftime()是逆操作。在这个函数中，format默认为："%a %b %d %H:%M:%S %Y"

import time
test_g = time.strptime("2018-12-18 21:26:50","%Y-%m-%d %H:%M:%S")
print(test_g)

# 程序执行结果
time.struct_time(tm_year=2018, tm_mon=12, tm_mday=18, tm_hour=21, tm_min=26, tm_sec=50, tm_wday=1, tm_yday=352, tm_isdst=-1)
```

### 其他内置方法

关于 `time`模块还有一些其他常用的方法，具体如下描述：

**time.sleep()**

该方法用于延迟时间：

```python
import time

time.sleep(5)
# 表示延迟5秒
```

**clock()**

这个需要注意，在不同的系统上含义不同。在UNIX系统上，它返回的是“进程时间”，它是用秒表示的浮点数（时间戳）。而在WINDOWS中，第一次调用，返回的是进程运行的实际时间。而第二次之后的调用是自第一次调用以后到现在的运行时间，即两次时间差。

```python
# Unix 系统
import time
test_h = time.clock()
print(test_h)

# 程序执行结果
0.082935

# WINDOWS 系统
import time
test_i = time.clock()
print(test_i）

# 程序执行结果
22.4396926
```

> 需要注意的是该方法在3.3版本以后将被移除


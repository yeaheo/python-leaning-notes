# random 模块

`random`模块是随机模块，其输出值为指定范围内的随机数，常用的方法有几种，具体如下：

**random.random()**

该方法表示输出随机数，范围是`0-1`，类型为浮点数：

```python
import random

print(random.random())

# 程序执行结果
第一次：0.24919147851055778
第二次：0.7996485400843928
```

**random.uniform()**

该方法类似 `random.random()`方法，其输出值为指定范围内的浮点数：

```python
import random

randd = random.uniform(1,3)
print(randd)

# 程序执行结果
第一次：2.298388684253614
第二次：2.9158421759074096
```

**random.randint()**

该方法用于输出指定区间的整数，取值范围相当于闭区间，左右值都可以取到：

```python
import random
randa = random.randint(1,3)
print(randa)

# 程序执行结果
第一次：1
第二次：3
```

**random.randrange()**

该方法类似 `random.randint()` 同样是输出指定区间内的整数，不同的是该方法取值范围为包括左不包括右，例如（1，3）取值范围为 `1=<x<3`:

```python
import random
randb = random.randrange(1,3)
print(randb)

# 程序执行结果
第一次：2
第二次：1
# 取不到 3
```


# reduce函数

reduce()函数一般用来将序列中的元素合并到一起，可以指定初始值。

```python
# reduce()函数类似
from functools import reduce
num = [1,2,3,4,100]
a = reduce(lambda x,y:x+y,num,1)
b = reduce(lambda x,y:x+y,num)
print(a)
print(b)

# 程序执行结果
111
110
```


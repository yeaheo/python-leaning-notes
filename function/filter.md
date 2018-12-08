# filter函数

filter() 函数一般用来筛选序列中的元素，其原理是循环遍历序列中的每个元素，判断每个元素是否符合指定条件，然后返回布尔值，如果是 True 则留下来，如果是 False 则丢弃。

```python
# filter() 函数原理
li = ['alex_sb','lv','eric_sb','hello']
def a(x):
    return x.endswith('sb')

def movi(func,arrary):
    ab = []
    for i in arrary:
        if not a(i):
            ab.append(i)
    return ab

a = movi(a,li)
print(a)
```

真正的 filter() 函数

```python
# 真正的filter函数
b = filter(lambda x:not x.endswith('sb'),li)
print(list(b))
```


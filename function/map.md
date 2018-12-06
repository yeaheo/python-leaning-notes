# map函数

```python
# map()函数原理
li = [1,2,3,4,5,6]
lambda x:x+1
def map_test(func,arrary):
    li_test = []
    for i in arrary:
        res = func(i)
        li_test.append(res)
    return li_test

a = map_test(lambda x:x+1,li)
b = map_test(lambda x:x**2,li)
print(a)
print(b)
```

真正的 `map`函数：

```python
c = map(lambda x:x+1,li)
print(c)
d = list(c)
print(d)
```


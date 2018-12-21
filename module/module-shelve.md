# shelve 模块

shelve 模块相比 pickle 模块简单，只有一个 open() 的方法，其返回值是类似字典的对象，可读可写，其key必须为字符串，而值可以是 python 所支持的数据类型。

```python
import shelve

f = shelve.open('shelve_text')
f['info'] = {'name': 'James','age': '22'}
print(f['info'])

# 程序执行结果
{'name': 'James', 'age': '22'}
```


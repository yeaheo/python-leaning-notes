# 字典-dict

字典是另一种可变容器模型，且可存储任意类型对象。字典的每个键值(key=>value)对用冒号(**:**)分割，每个对之间用逗号(**,**)分割，整个字典包括在花括号(**{})**中。

关于字典的键值存储：键必须是唯一的，但值则不必。值可以取任何数据类型，但键必须是不可变的，如字符串，数字或元组（布尔值也算）。

需要注意的是字典是无序的

不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住

键必须不可变，所以可以用数字，字符串或元组充当，而用列表就不行

## 字典的一般用法

**取值:**

字典可以根据索引进行取值：

```python
d = {"name":"lvxiaoteng","age": 25,"website":"https://yeaheo.com"}
v1 = d['name']
v2 = d['website']
v3 = d['hah']
print(d)
print(v1)
print(v2)
print(v3)

# 程序执行结果
{'name': 'lvxiaoteng', 'age': 25, 'website': 'https://yeaheo.com'}
lvxiaoteng
https://yeaheo.com
```

> 需要注意的是字典是无序的，不能进行索引切片

**删除**

删除字典中的某个键，可以用 `del`，参考示例如下：

```python
d = {"name":"lvxiaoteng","age": 25,"website":"https://yeaheo.com"}
del d['age']
print(d)

# 程序执行如下
{'name': 'lvxiaoteng', 'website': 'https://yeaheo.com'}

# 删除整个字典
del d
```

**迭代**

字典也是可迭代的，可以用 `for`循环输出键或者值：

```python
d = {"name":"lvxiaoteng","age": 25,"website":"https://yeaheo.com"}
for i in d:
    print(i)

# 程序输出如下
name
age
website

效果同：
d = {"name":"lvxiaoteng","age": 25,"website":"https://yeaheo.com"}
for i in d.keys():
    print(i)
```

默认情况下只迭代的是键，没有值，如果需要迭代其值，可以参考如下实例：

```python
d = {"name":"lvxiaoteng","age": 25,"website":"https://yeaheo.com"}
for i in d.values():
    print(i)

# 程序执行如下
lvxiaoteng
25
https://yeaheo.com
```

如果需要迭代字典的键和值，可以参考 `dict.items()`方法：

```python
d = {"name":"lvxiaoteng","age": 25,"website":"https://yeaheo.com"}
for x,y in d.items():
    print(x,y)
    
# 程序执行结果
name lvxiaoteng
age 25
website https://yeaheo.com
```

**修改字典**

向字典添加新内容的方法是增加新的键/值对，修改或删除已有键/值对如下实例:

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
d['age'] = 24  # 更新值
d['school'] = 'Tangshan University' # 增加新值
print(d)

# 程序执行结果
{'name': 'lvxiaoteng', 'age': 24, 'site': 'https://yeaheo.com', 'school': 'Tangshan University'}
```

## 字典常用的方法

**len(dict)**

计算字典元素个数，即键的总数:

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v = len(d)
print(v)

# 程序执行结果
3
```

**str(dict)**

输出字典，以可打印的字符串表示：

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v = str(d)
print(v)

# 程序执行结果
{'name': 'lvxiaoteng', 'age': 25, 'site': 'https://yeaheo.com'}
```

**type(variable)**

返回输入的变量类型，如果变量是字典就返回字典类型：

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v = type(d)
print(v)

# 程序执行结果
<class 'dict'>
```

**clear()**

该方法用于清空字典：

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
d.clear()
print(d)

# 程序执行结果
{}
```

**copy()**

该方法用于复制（浅复制），类似于列表：

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v = d.copy()
print(v)

# 程序执行结果
{'name': 'lvxiaoteng', 'age': 25, 'site': 'https://yeaheo.com'}
```

**get()**

该方法用于获取某个键对应的值，也可以指定不存在的键的返回值：

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v = d.get('name')
print(v)

# 程序执行结果
lvxiaoteng
```

```python
# 指定当 key 不存在时的返回值
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v1 = d.get('name')
v2 = d.get('haha',900)
print(v1)
print(v2)

# 程序执行结果
lvxiaoteng
900
```

**fromkeys()**

Python 字典 `fromkeys()` 函数用于创建一个新字典，以序列seq中元素做字典的键，value为字典所有键对应的初始值，该方法返回列表。

格式：dict.fromkeys(seq[, value])

- seq -- 字典键值列表。
- value -- 可选参数, 设置键序列（seq）的值。

```python
seq = ('name','age','website')
v = dict.fromkeys(seq)
print(v)

# 程序执行结果
{'name': None, 'age': None, 'website': None} # 默认只有键没有值


seq = ('name','age','website')
v = dict.fromkeys(seq，100)
print(v)

# 程序执行结果
{'name': 10, 'age': 10, 'website': 10}
```

**items()**

该方法用于获取字典的键和值：

```python
# 示例1
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v = d.items()
print(v)

# 程序执行结果
dict_items([('name', 'lvxiaoteng'), ('age', 25), ('site', 'https://yeaheo.com')])

# 示例2
d = {"name":"lvxiaoteng","age": 25,"website":"https://yeaheo.com"}
for x,y in d.items():
    print(x,y)
    
# 程序执行结果
name lvxiaoteng
age 25
website https://yeaheo.com
```

**keys()**

该方法用于获取字典的键：

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
for i in d.keys():
    print(i)

# 程序执行结果
name
age
site
```

**pop()**

该方法用于删除字典的指定的 key,可以获取删除的键和值,可以指定返回默认值

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v = d.pop('age')
print(v)
print(d)

# 程序执行结果
25
{'name': 'lvxiaoteng', 'site': 'https://yeaheo.com'}

d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v1 = d.pop('age',90)
v2 = d.pop('hah',90)
print(v1)

# 程序执行结果
25
90
```

**popitem()**

Python 字典 popitem() 方法随机返回并删除字典中的一对键和值(一般删除末尾对)。如果字典已经为空，却调用了此方法，就报出KeyError异常。

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v = d.popitem()
print(v)
print(d)

# 程序执行结果
('site', 'https://yeaheo.com')
{'name': 'lvxiaoteng', 'age': 25}
```

**setdefault()**

Python 字典 setdefault() 方法和`get()`类似, 如果键不已经存在于字典中，将会添加键并将值设为默认值。

语法：dict.setdefault(key, default=None)

如果 key 在 字典中，返回对应的值。如果不在字典中，则插入 key 及设置的默认值 default，并返回 default ，default 默认值为 None。

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
v1 = d.setdefault('name',100)
v2 = d.setdefault('haha',100)
print(v1)
print(v2)
print(d)

# 程序执行结果
lvxiaoteng
100
{'name': 'lvxiaoteng', 'age': 25, 'site': 'https://yeaheo.com', 'haha': 100}
```

**update()**

该方法用于更新字典：

```python
#示例1
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
d.update({'haha':100,'soc':550})
print(d)

# 程序执行结果
{'name': 'lvxiaoteng', 'age': 25, 'site': 'https://yeaheo.com', 'haha': 100, 'soc': 550}

#示例2
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
d.update(haha=100,soc=550)
print(d)

# 程序执行结果
{'name': 'lvxiaoteng', 'age': 25, 'site': 'https://yeaheo.com', 'haha': 100, 'soc': 550}
```

**values()**

此方法类似 `items()`和`keys()`用于获取字典的值：

```python
d = {'name':'lvxiaoteng','age': 25,'site':'https://yeaheo.com'}
for i in d.values():
    print(i)

# 程序执行结果
lvxiaoteng
25
https://yeaheo.com
```


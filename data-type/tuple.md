# 元组-tuple

Python 的元组与列表类似，不同之处在于元组的元素不能修改。元组使用小括号，列表使用方括号。元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可。

元组是有序的，但是元素不能被修改/增加/删除。

为了不与函数参数冲突，建议在创建元组的时候在最后一个元素后补上一个 `,`

与字符串一样，元组之间可以使用 + 号和 * 号进行运算。这就意味着他们可以组合和复制，运算后会生成一个新的元组。

## 元组基本使用技巧

创建空元组：

```python
tup1 = ();
```

>元组中只包含一个元素时，需要在元素后面添加逗号，否则括号会被当作运算符使用：

元组中的元素值是不允许修改的，但我们可以对元组进行连接组合，如下实例:

```python
t1 = (1,2,3,4,)
t2 = ("abc","dfg",)
t3 = t1 + t2
print(t3)

# 程序执行结果
(1, 2, 3, 4, 'abc', 'dfg')
```

元组中的元素值是不允许删除的，但我们可以使用del语句来删除整个元组，如下实例：

```python
t = (1,2,34,4,)
del t
print(t)

# 程序执行结果
Traceback (most recent call last):
  File "E:/MyPy/venv/list.py", line 64, in <module>
    print(t)
NameError: name 't' is not defined
```

元组与列表类似，可以利用索引和切片取值,切片返回值依然为元组：

```python
t = (1,2,3,4,'abc')
v1 = t[1]
v2 = t[1:4]
print(v1)
print(v2)

# 程序执行结果
2
(2, 3, 4)
```

元组也是可迭代对象，所以可以使用 `for`和 `while`循环：

```python
t = (1,2,3,4,'abc')
for i in t:
    print(i)

# 程序执行结果
1
2
3
4
abc
```

元组可以和字符串和列表互相转换：

```python
# 元组——字符串  此方法和列表转换为字符串类似，不再赘述
# 元组转换成列表
t = (1,2,3,4,'abc')
li = list(t)
print(li)

# 程序执行结果
[1, 2, 3, 4, 'abc']
```

```python

# 字符串转换为元组
a = "abcdefg"
b = tuple(a)
print(b)

# 程序执行结果
('a', 'b', 'c', 'd', 'e', 'f', 'g')
```

```python

# 列表转换为元组
li = [1,2,34,'abc']
t = tuple(li)
print(t)

# 程序执行结果
(1, 2, 34, 'abc')
```

## 元组内置方法与函数

**len(tuple)**

该方法用于计算元组元素数量：

```python
t = (1,2,34,4,)
v = len(t)
print(v)

# 程序执行结果
4
```

**max(tuple)**

该方法用于取出元组中元素最大值：

```python
t = (1,2,34,4,)
v = max(t)
print(v)

# 程序执行结果
34
```

**min(tuple)**

该方法用于取出元组中元素最小值

```python
t = (1,2,34,4,)
v = max(t)
print(v)

# 程序执行结果
1
```

**count()**

该方法用于统计列表中指定元素的个数：

```python
li = (1,'abc',3,4,3,1,2,3)
v1 = li.count(3)
v2 = li.count(1)
print(v1)
print(v2)

# 程序执行结果
3
2
```

**index()**

该方法用于查找列表中指定字符的索引，默认只是显示第一个索引：

```python
li1 = (1,'abc',3,4,3,1,2,3)
v = li1.index(3)
print(v)

# 程序执行结果
2
```

**enumerate()**

该方法用于显示列表、元组等的索引和值，可以指定索引值，后面依次增加：

```python
tu = ("alex","eric","rain")
for index,elem in enumerate(tu,10):
    print(index,elem)
# 程序执行结果
10 alex
11 eric
12 rain
```


# 集合-set

集合（set）是一个无序的不重复元素序列。

可以使用大括号 `{ }` 或者 `set()` 函数创建集合，注意：创建一个空集合必须用 `set()` 而不是 `{ }`，因为` { }` 是用来创建一个空字典。`set()`参数必须为可迭代类型。

集合中的元素必须是不可变类型：数字、字符串、元组

创建格式：

```python
parame = {value01,value02,...}
或者
set(value)
```

例如：

```python
a = set('abc')
print(a)

# 程序输出结果
{'c', 'b', 'a'}  # 可以看到集合是无序的

b = {'a',1,2,3}
print(b)

# 程序执行结果
{1, 2, 3, 'a'}

# 创建空集合
c = set()
print(c)

# 程序输出结果
set()
```

集合也是可遍历的，也可以使用 `in`来判断某元素是否在集合里，集合的元素也是不重复的：

```python
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
print(basket)
a = 'apple' in basket
b = 'aaa' in basket
print(a)
print(b)

# 程序执行结果
{'banana', 'orange', 'pear', 'apple'}   # 集合元素不重复
True
False
```

可以用 `len()` 查看集合元素个数：

```python
s = {1,2,3,'abc',4}
a = len(s)
print(a)

# 程序执行结果
5
```

## 集合一般运算

集合的运算一般包括：交集、并集、差集、交叉补集

现在定义两个集合：

```python
s1 = {'alex','eric','tony','brain'}
s2 = {'eric','abc','tony','apple'}
```

**交集**

**intersection() 或  `&`**

交集即既存在于 `s1`也存在于 `s2`中的元素：

```python
s1 = {'alex','eric','tony','brain'}
s2 = {'eric','abc','tony','apple'}
a = s1.intersection(s2)
b = s1 & s2
print(a)
print(b)

# 程序执行结果
{'tony', 'eric'}
{'tony', 'eric'}
```

**并集**

**union() 或 `|`**

并集即集合 `s1` 或 `s2`中包含的所有元素:

```python
s1 = {'alex','eric','tony','brain'}
s2 = {'eric','abc','tony','apple'}
a = s1.union(s2)
b = s1 | s2
print(a)
print(b)

# 程序执行结果
{'abc', 'alex', 'tony', 'brain', 'apple', 'eric'}
{'abc', 'alex', 'tony', 'brain', 'apple', 'eric'}
```

**差集**

**difference() 或 `-`**

差集即例如 `s1-s2`表示存在 `s1`但不存在 `s2`中的元素：

```python
s1 = {'alex','eric','tony','brain'}
s2 = {'eric','abc','tony','apple'}
a = s1.difference(s2)
b = s1 - s2
print(a)
print(b)

# 程序执行结果
{'alex', 'brain'}
{'alex', 'brain'}

---------------------
s1 = {'alex','eric','tony','brain'}
s2 = {'eric','abc','tony','apple'}
a = s2.difference(s1)
b = s2 - s1
print(a)
print(b)

# 程序执行结果
{'abc', 'apple'}
{'abc', 'apple'}
```

**交叉补集**

**symmetric_difference() 或 `^`**

交叉补集是指不同时包含于 `s1`和 `s2`的元素:

```python
s1 = {'alex','eric','tony','brain'}
s2 = {'eric','abc','tony','apple'}
a = set.symmetric_difference(s1,s2)
b = s1 ^ s2
print(a)
print(b)

# 程序执行结果
{'abc', 'alex', 'brain', 'apple'}
{'abc', 'alex', 'brain', 'apple'}
```

## 集合内置方法

**add()**

该方法用于向集合中增加元素，增加的元素必须是单个元素(顺序随机),如果元素已存在，则不进行任何操作。

```python
s = {'eric','abc','tony','apple'}
s.add('hehi')
print(s)

# 程序执行结果
{'apple', 'hehi', 'eric', 'tony', 'abc'}
```

> 区别于 `update`方法

 **update()**

该方法也是向集合中添加元素，但参数可以是列表，元组，字典等，可以更新多个值，语法格式如下：

```python
s = {1,2,3,'abc'}
s.update(['hello','ak47'])
print(s)

# 程序执行结果
{1, 2, 3, 'abc', 'ak47', 'hello'}
----------------------------------
s = {1,2,3,'abc'}
s.update(('hello','ak47'))
print(s)

# 程序执行结果
{1, 2, 3, 'abc', 'ak47', 'hello'}
----------------------------------
s = {1,2,3,'abc'}
s.update({'name': 'lv','age': 25})
print(s)

# 程序执行结果
{1, 2, 3, 'abc', 'age', 'name'}
```

**clear()**

清空集合：

```python
s = {1,2,3,'abc'}
s.clear()
print(s)

#程序执行结果
set()
```

**copy()**

复制集合（浅复制）

```python
s = {1,2,3}
a = s.copy()
print(a)

# 程序执行结果
{1,2,3}
```

**difference()*  和  difference_update() **

difference()用于求差集，可以参考上面相关内容,默认不更改原集合元素

difference_update()用于求差集并更新原集合，参考如下：

```python
s1 = {'alex','eric','tony','brain'}
s2 = {'eric','abc','tony','apple'}
s1.difference_update(s2)
print(s1)

#程序执行结果
{'alex', 'brain'}
```

**pop()    remove()    和  discard()**

该三种方法都是用来删除集合中的元素的，不同的是：

- pop() 用于删除集合中某一元素，随机删除,可以获取删除的元素
- remove() 用于删除集合中指定元素，当元素不存在时报错
- discard()也是用于删除集合中指定元素，当元素不存在时不报错

```python
# pop()
s = {'alex','eric','tony','brain'}
v = s.pop()
print(v)
print(s)

# 程序执行结果
tony
{'alex', 'brain', 'eric'}
```

```python
# remove()
s = {'alex','eric','tony','brain'}
v = s.remove('alex')
print(v)
print(s)

# 程序执行结果
None # 不能获取删除的值
{'tony', 'brain', 'eric'}
---------------------------------------
s = {'alex','eric','tony','brain'}
s.remove('aalex')  # 当集合元素不存在时报错
print(s)

# 程序执行结果
Traceback (most recent call last):
  File "E:/MyPy/venv/list.py", line 295, in <module>
    s.remove('aalex')
KeyError: 'aalex'

```

```python
# remove()
s = {'alex','eric','tony','brain'}
v = s.discard('alex')
print(v)
print(s)

# 程序执行结果
None # 不能获取删除的值
{'tony', 'brain', 'eric'}
---------------------------------------
s = {'alex','eric','tony','brain'}
s.discard('aalex')  # 当集合元素不存在时不报错
print(s)

# 程序执行结果
{'brain', 'alex', 'eric', 'tony'}
```

**intersection() 和 intersection_update()**

intersection()用于求交集，不更新原集合

intersection_update() 用于求集合交集并更新原集合，类似difference_update(）不再赘述

**symmetric_difference() 和 symmetric_difference_update()**

symmetric_difference()用于求集合的交叉补给，可以参考上述集合运算方法，不改变原集合

symmetric_difference_update()用于求集合的交叉补给，类似difference_update(）不再赘述

**isdisjoint()**

该方法用于判断两个集合交集是否为空，当为空时返回 True，否则返回 False：

```python
s1 = {1,2,3}
s2 = {4,5,6}
s3 = {1,3,4}
a = s1.isdisjoint(s2)
b = s1.isdisjoint(s3)
print(a)
print(b)

# 程序执行结果
True
False
```

**issubset() 和 issuperset()**

issubset()用于判断两个集合父子集关系，当 `s1`是 `s2`的子集的时候，`s1.issubset(s2)`返回 `True`，反之返回 `False` 相当于 `s1 <= s2`

issuperset()和issubset()相反，相当于 `s1 >= s2`

```python
s1 = {1,2,3}
s2 = {1,2,3,4}
s3 = {1,2,3,4,5}
v1 = s1.issubset(s2)
v2 = s2.issubset(s1)
v3 = s3.issuperset(s1)
v4 = s1.issuperset(s3)
print(v1,v2,v3,v4)

# 程序执行结果
True False True False
```




# 列表-list

序列是 Python 中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是 0，第二个索引是 1，依此类推。Python 有 6 个序列的内置类型，但最常见的是列表和元组。

序列都可以进行的操作包括索引，切片，加，乘，检查成员。此外，Python 已经内置确定序列的长度以及确定最大和最小的元素的方法。列表是最常用的 Python 数据类型，它可以作为一个方括号内的逗号分隔值出现。列表的数据项不需要具有相同的类型。

### 列表常用的技巧

我们可以通过索引和切片的方式获取列表中的元素：

```python
li = [1,2,3,'abc','lv']
v1 = li[1]
v2 = li[2:4]
print(v1)
print(v2)

# 程序执行结果
2
[3, 'abc']
```

当然，我们也可以通过索引和切片的方式删除列表中的元素：

```python
li = [1,2,3,'abc','lv']
del li[1]
print(li)

# 程序执行结果
[1, 3, 'abc', 'lv']

li = [1,2,3,'abc','lv']
del li[1:3]
print(li)

# 程序执行结果
[1, 'abc', 'lv']
```

列表也可以通过 for 、while 循环输出元素：

```python
# for 循环
li = [1,2,3,'abc','lv']
for i in li:
    print(i)

# 程序执行结果
1
2
3
abc
lv
```

```python
li = [1,2,3,'abc','lv']
count = 0
while count < len(li):
    print(li[count])
    count = count + 1

# 程序执行结果
1
2
3
abc
lv
```

**列表转换成字符串：**

当列表中的元素全部为字符串时，我们可以利用 字符串的 `join`方法将列表中的元素拼接为字符串：

```python
li = ['abc','defg','acv','qir']
v = "".join(li)
print(v)

# 程序执行结果
abcdefgacvqir
```

当列表中的元素有字符串和数字时，我们可以自己写 `for` 循环将列表中的元素拼接为字符串：

```python
s = ""
li = ['abc',1,2,3]
for i in li:
    s = s + str(i)
print(s)

# 程序执行结果
abc123
```

列表支持 `in`操作：

```python
li = ['abc','1',2]
v1 = 2 in li
v2 = 3 in li
print(v1)
print(v2)

# 程序执行结果
True
False
```

> 列表转换其实用的是 `for` 循环，`join`其实用的也是 `for`循环

### 列表常用的方法

列表中也有好多方法，在此记录一下方便后期查阅，具体方法用途可以参考如下：

**append(self, \*args, \*\*kwargs)**

该方法用于在列表中新增元素，默认加在列表末尾：

```python
li = [1,2,3,"abc"]
li.append("we")
print(li)

# 程序执行结果
[1, 2, 3, 'abc', 'we']
```

**clear(self, \*args, \*\*kwargs)**

该方法用于清空列表：

```python
li = [1,2,3,4]
li.clear()
print(li)

# 程序执行结果
[]
```

**copy(self, \*args, \*\*kwargs)**

该方法用于复制列表（浅复制）：

```python
li = [1,'abc',3,4]
v = li.copy()
print(v)

# 程序执行结果
[1, 'abc', 3, 4]
```

**count(self, \*args, \*\*kwargs)**

该方法用于统计列表中指定元素的个数：

```python
li = [1,'abc',3,4,3,1,2,3]
v1 = li.count(3)
v2 = li.count(1)
print(v1)
print(v2)

# 程序执行结果
3
2
```

**extend(self, \*args, \*\*kwargs)**

该方法用于扩展列表：

```python
li1 = [1,'abc',3,4,3,1,2,3]
li2 = ['uc','qq']
li1.extend(li2)
print(li1)

# 程序执行结果
[1, 'abc', 3, 4, 3, 1, 2, 3, 'uc', 'qq']
```

>  需要注意的是，经扩展的列表没有变化，依旧是 `li1`，直接输出即可，不要再赋值给其他变量，注意与 `append()`方法的区别，前者是扩展，后者直接增加元素，可扩展的元素需要是可迭代对象

**index(self,\ *args,\ *\*kwargs)**

该方法用于查找列表中指定字符的索引，默认只是显示第一个索引：

```python
li1 = [1,'abc',3,4,3,1,2,3]
v = li1.index(3)
print(v)

# 程序执行结果
2
```

**insert()**

该方法用于向列表指定位置插入数值：

```python
li = [1,2,3]
li.insert(1,'abc')
print(li)

# 程序执行结果
[1, 'abc', 2, 3]
```

**pop()**

该方法用于删除列表中某个索引对应的元素,默认删除最后一个元素，删除的元素可以获取到：

```python
li = [1,2,3]
v = li.pop()
print(v)
print(li)

# 程序执行结果
3
[1, 2]

li = [1,2,3]
v = li.pop(1) # 删除索引为 1 的元素
print(v)
print(li)

# 程序执行结果
2
[1, 3]
```

**remove()**

该方法用于删除列表中指定的值，注意与 `pop()`方法做区分：

```python
li = [1,2,3,'abc']
li.remove('abc')
print(li)

# 程序执行结果
[1, 2, 3]
```

**reverse()**

该方法用于将列表中的元素做反转：

```python
li = [1,2,3,'abc']
li.reverse()
print(li)

# 程序执行结果
['abc', 3, 2, 1]
```

**sort()**

该方法用于将列表中的元素按照一定顺序进行排序，默认是顺序：

```python
li = [1,3,4,2,5,2,7]
li.sort()
print(li)

# 程序执行结果
[1, 2, 2, 3, 4, 5, 7]

li = [1,3,4,2,5,2,7]
li.sort(reverse=True)  # 逆序排序
print(li)

# 程序执行结果
[7, 5, 4, 3, 2, 2, 1]
```

> `sort()`方法还有 `cmp`和`key`参数，后期会更新....


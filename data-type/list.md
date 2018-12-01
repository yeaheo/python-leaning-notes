# 列表-list

序列是 Python 中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是 0，第二个索引是 1，依此类推。Python 有 6 个序列的内置类型，但最常见的是列表和元组。

序列都可以进行的操作包括索引，切片，加，乘，检查成员。此外，Python 已经内置确定序列的长度以及确定最大和最小的元素的方法。列表是最常用的 Python 数据类型，它可以作为一个方括号内的逗号分隔值出现。列表的数据项不需要具有相同的类型。

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

>  需要注意的是，经扩展的列表没有变化，依旧是 `li1`，直接输出即可，不要再赋值给其他变量

**index(self,\ *args,\ *\*kwargs)**

该方法用于查找列表中指定字符的索引，默认只是显示第一个索引：

```python
li1 = [1,'abc',3,4,3,1,2,3]
v = li1.index(3)
print(v)

# 程序执行结果
2
```


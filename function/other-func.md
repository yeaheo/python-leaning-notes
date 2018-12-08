# 其他内置函数

Python 中还内置了很多函数，我主要记录了几个，参考如下：

**abs()**函数

该函数用来取绝对值：

```python
a = 1
b = -10
print(abs(a))
print(abs(b))

# 程序执行结果
1
10
```

**all()**函数

该函数主要用来判断参数的真假值，当给定的参数中布尔值全部为 `True`则为 `True`，有一个为 `False` 则为 `False`

如果可迭代对象为空也为 `True`

```python
a = ""
b = 1
c = ['1',2,'abc']
d = []
print(bool(a),bool(b),bool(c),bool(d))
print(all(a))
print(all([1,2,""]))
print(all())

# 程序执行结果
False True True False
True
False
```

**bin()**函数

该函数主要是将指定值转化为二进制表示：

```python
test = 10
print(bin(test))

# 程序执行结果
0b1010
```

**oct()**函数

该函数主要是将指定值转化为八进制表示：

```python
test = 10
print(oct(test))

# 程序执行结果
0o12
```

**hex()** 函数

该函数主要是将指定值转化为十六进制表示：

```python
test = 20
print(hex(test))

# 程序执行结果
0x14
```

**bytes()** 函数

该函数主要是将指定参数转为位数表示，需要指定 `encoding`：

```python
test1 = 'hello'
test2 = "你好"
print(bytes(test1,encoding='utf-8'))
print(bytes(test2,encoding='utf-8'))

# 程序执行结果
b'hello'
b'\xe4\xbd\xa0\xe5\xa5\xbd'
```

**encode()**函数

encode() 方法以指定的编码格式编码字符串。errors 参数可以指定不同的错误处理方案。

encode()方法语法：str.encode(encoding='UTF-8',errors='strict')

- encoding -- 要使用的编码，如: UTF-8。
- errors -- 设置不同错误的处理方案。默认为 'strict',意为编码错误引起一个UnicodeError。 其他可能得值有 'ignore', 'replace', 'xmlcharrefreplace', 'backslashreplace' 以及通过 codecs.register_error() 注册的任何值。

该方法返回编码后的字符串，它是一个 bytes 对象。

```python
str_test = "你好"
print(str_test.encode("utf-8"))
print(str_test.encode('GBK'))

# 程序执行结果
b'\xe4\xbd\xa0\xe5\xa5\xbd'
b'\xc4\xe3\xba\xc3'
```

**decode()**函数

decode() 方法以指定的编码格式解码 bytes 对象。默认编码为 'utf-8'。该方法与 encode() 函数相反。

decode()方法语法：bytes.decode(encoding="utf-8", errors="strict")

- encoding -- 要使用的编码，如"UTF-8"。
- errors -- 设置不同错误的处理方案。默认为 'strict',意为编码错误引起一个UnicodeError。 其他可能得值有 'ignore', 'replace', 'xmlcharrefreplace', 'backslashreplace' 以及通过 codecs.register_error() 注册的任何值。

该方法返回解码后的字符串。

```python
str_test = "你好"
a = str_test.encode("utf-8")
b = str_test.encode('GBK')
c = a.decode('utf-8')
d = b.decode('GBK')
print(c)
print(d)

# 程序执行结果
你好
你好
```

> 需要注意的是编码和解码需要一致

**chr()**函数

该函数用一个范围在 range（256）内的（就是0～255）整数作参数，返回一个对应的字符。其参数可以是十进制或者十六进制形式的数字，返回值是当前整数对应的ascii字符。

```python
a = chr(100)
b = chr(97)
print(a)
print(b)

# 程序输出结果
d
a
```

**ord()**函数

ord() 函数是 chr() 函数（对于8位的ASCII字符串）或 unichr() 函数（对于Unicode对象）的配对函数，它以一个字符（长度为1的字符串）作为参数，返回对应的 ASCII 数值，或者 Unicode 数值，如果所给的 Unicode 字符超出了你的 Python 定义范围，则会引发一个 TypeError 的异常。

ord()的参数为字符，返回值是对应的十进制整数。

```python
c = 100
d = 97
print(ord(c))
print(ord(d))

# 程序执行结果
100
97
```

**dir()**函数

**dir()** 函数不带参数时，返回当前范围内的变量、方法和定义的类型列表；带参数时，返回参数的属性、方法列表。如果参数包含方法__dir__()，该方法将被调用。如果参数不包含__dir__()，该方法将最大限度地收集参数信息。

语法：dir([object])  

- object -- 对象、变量、类型。

返回模块的属性列表。

```python
#  获得当前模块的属性列表
print(dir())

# 程序输出结果
['__annotations__', '__builtins__', '__cached__', '__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', 'li', 'os']

# 查看列表的方法
print(dir([]))

# 程序输出结果
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', ...]
```

**divmod()**函数

python divmod() 函数把除数和余数运算结果结合起来，返回一个包含商和余数的元组(a // b, a % b)。

在 python 2.3 版本之前不允许处理复数。

```python
a = 10
b = 7
c = divmod(a,b)
print(c)

# 程序执行结果
(1, 3)
```

**eval()**函数

eval() 函数用来执行一个字符串表达式，并返回表达式的值。

```python
print(eval('10+10'))
print(eval('2**2'))

# 程序执行结果
20
4
```

**hash()**函数

可hash的数据类型为不可变类型，不可hash的数据类型为可变数据类型
长度不可变
不可逆
变量不变 hash 不变

```python
print(hash('test'))
print(hash('test1'))

# 程序执行结果
-8884452091179381303
1923469092038480646
```

**isinstance()**函数

isinstance() 函数来判断一个对象是否是一个已知的类型，类似 type()。

```python
a = 'test'
b = [1,2,3,4]
print(isinstance(a,str))
print(isinstance(b,list))

# 程序执行结果
True
True
```

**len()**函数

该函数用于返回参数的长度：

```python
test = 'test'
print(len(test))

# 程序执行结果
4
```

> 需要注意的是该参数不能为 int 类型

**globals()**函数

**globals()** 函数会以字典类型返回当前位置的全部全局变量。

```python
a = 'lvxiaoteng'
print(globals())

# 程序执行结果
{...,'a': 'lvxiaoteng'}
```

**max() 函数和 min() 函数**

求最大值最小值

```python
a = [1,2,3,5,6,9,0]
print(max(a))
print(min(a))

# 程序执行结果
9
0
```

高级使用方式,取出某个字段对应的最大值和其其他附带值：

```python
dict_test = [{'name': 'lvxiaiteng','age': 25},
             {'name': 'harry', 'age': 26},
             {'name': 'alex', 'age': 87},
             {'name': 'eric', 'age': 100}]
print(max(dict_test,key=lambda dic:dic['age']))
print(min(dict_test,key=lambda dic:dic['age']))

# 程序执行结果
{'name': 'eric', 'age': 100}
{'name': 'lvxiaiteng', 'age': 25}
```

**open()**函数

python open() 函数用于打开一个文件，创建一个 file 对象，相关的方法才可以调用它进行读写

**slice()** 函数

该函数用于实现切片对象，主要用在切片操作函数里的参数传递。返回一个切片对象。

slice 语法：

```
class slice(stop)
class slice(start, stop[, step])

# 参数说明
start -- 起始位置
stop -- 结束位置
step -- 间距
```

```python
mysle = slice(5)
arr = range(10)
print(arr[mysle])

# 程序执行结果
range(0, 5)
```

**sorted()** 函数

该函数对所有可迭代的对象进行排序操作。

> sort 是应用在 list 上的方法，sorted 可以对所有可迭代的对象进行排序操作。
>
> list 的 sort 方法返回的是对已经存在的列表进行操作，无返回值，而内建函数 sorted 方法返回的是一个新的 list，而不是在原来的基础上进行的操作。

sorted 语法：sorted(iterable[, cmp[, key[, reverse]]])

参数说明：

- iterable -- 可迭代对象。
- cmp -- 比较的函数，这个具有两个参数，参数的值都是从可迭代对象中取出，此函数必须遵守的规则为，大于则返回1，小于则返回-1，等于则返回0。
- key -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。
- reverse -- 排序规则，reverse = True 降序 ， reverse = False 升序（默认）。

```python
>>>a = [5,7,6,3,4,1,2]
>>> b = sorted(a)       # 保留原列表
>>> a 
[5, 7, 6, 3, 4, 1, 2]
>>> b
[1, 2, 3, 4, 5, 6, 7]
 
>>> L=[('b',2),('a',1),('c',3),('d',4)]
>>> sorted(L, cmp=lambda x,y:cmp(x[1],y[1]))   # 利用cmp函数
[('a', 1), ('b', 2), ('c', 3), ('d', 4)]
>>> sorted(L, key=lambda x:x[1])               # 利用key
[('a', 1), ('b', 2), ('c', 3), ('d', 4)]
 
 
>>> students = [('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10)]
>>> sorted(students, key=lambda s: s[2])            # 按年龄排序
[('dave', 'B', 10), ('jane', 'B', 12), ('john', 'A', 15)]
 
>>> sorted(students, key=lambda s: s[2], reverse=True)       # 按降序
[('john', 'A', 15), ('jane', 'B', 12), ('dave', 'B', 10)]
>>>
```

**zip()**函数

**zip()** 函数用于将可迭代的对象作为参数，将对象中对应的元素打包成一个个元组，然后返回由这些元组组成的列表。

如果各个迭代器的元素个数不一致，则返回列表长度与最短的对象相同，利用 * 号操作符，可以将元组解压为列表。

> zip 方法在 Python 2 和 Python 3 中的不同：在 Python 3.x 中为了减少内存，zip() 返回的是一个对象。如需展示列表，需手动 list() 转换。

```python
a = [1,2,3,45]
b = ['a','b','c','d']
v = list(zip(b,a))
print(v)

# 程序执行结果
[('a', 1), ('b', 2), ('c', 3), ('d', 45)]
```


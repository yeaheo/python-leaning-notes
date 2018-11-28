# 字符串-str

字符串是以单引号`'`或双引号`"`括起来的任意文本，比如`'abc'`，`"xyz"`等等。需要注意的是，`''`或`""`本身只是一种表示方式，不是字符串的一部分，因此，字符串`'abc'`只有`a`，`b`，`c`这3个字符。如果`'`本身也是一个字符，那就可以用`""`括起来，比如`"I'm OK"`包含的字符是`I`，`'`，`m`，空格，`O`，`K`这6个字符。

其实字符串本身有许多方法，这里我只是记录了几个方便后期回来复查，具体方法如下：

**capitalize()**

该方法表示将字符串首字母变为大写：

```python
test = 'lvxiaoteng'
v = str.capitalize(test)
print(v)

# 程序执行结果
Lvxiaoteng
```

**casefold()** 和**lower()** 

这两种方法均表示将大写字符串变为小写：

```python
c = "ALex"
v1 = str.casefold(c)
v2 = str.lower(c)
print(v1)
print(v2)

# 程序执行结果
alex
alex
```

> 不同的是 `casefold()`比 `lower()` 功能更加丰富，它可以将其他国家的语言大写转化为小写，而 `lower()` 貌似只能转化字母

**upper() 和 isupper()**

`upper()`方法是将字符串中的小写变成大写，`isupper()`方法是判断是否为大写，返回值为布尔值

```python
test = "abc"
v = test.upper()
v1 = v.isupper()
print(v)
print(v1)

# 程序执行结果
ABC
True
```

**str.center(width[, fillchar])**

该方法返回一个指定宽度 width 并且指定的字符串居中的字符串，fillchar 为填充的字符，默认为空格：

```python
test = "ABC"
v = test.center(21)
print(v)
v1 = test.center(21,'*')
print(v1)

# 程序执行结果
        ABC         
*********ABC*********
```

> 需要注意的是返回的字符串长度是指定的宽度，而且原字符串居中，其他空缺用指定的字符填充，默人空格

**count(self, sub, start=None, end=None)**

该方法表示对指定字符串的指定字符计数，默认是整个字符串，也可以指定`start`和`end`参数控制字符串区间：

```python
test =  "acxcxunci"
v = test.count('x')
print(v)
v1 = test.count('x',3,5)
print(v1)

# 程序执行结果
2
1
```

**endswith(self, suffix, start=None, end=None)**

该方法表示是否以指定字符串结尾，结果返回布尔值（True或False）：

```python
test = "cxucx"
v1 = test.endswith('x')
v2 = test.endswith('s')
print(v1,v2)

# 程序执行结果
True False
```

**startswith(self, prefix, start=None, end=None)**

该方法表示是否以指定字符串开头，结果返回布尔值（True或False）：

```python
test = "cxucx"
v1 = test.startswith('c')
v2 = test.startswith('s')
print(v1,v2)

# 程序执行结果
True False
```

**join(self, ab=None, pq=None, rs=None)**

该方法用来用指定字符插入到现有字符中：

```python
test = "你是风儿我是沙"
t = "_"
v = t.join(test)
print(v)

# 程序执行结果
你_是_风_儿_我_是_沙
```

**expandtabs(self, \*args, \*\*kwargs)**

该方法表示把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8 :

```python
test = "cuxzcz\tcxc\tnxc\t"
v1 = test.expandtabs()
v2 = test.expandtabs(6)
print(v1)
print(v2)

# 程序执行结果
cuxzcz  cxc     nxc     
cuxzcz      cxc   nxc   
```

**find(self, sub, start=None, end=None) 和 rfind()**

该方法表示查找字符串中的指定字符，返回被查找字符的第一个索引值，可以指定 `start`和`end`指定查找区间，如果未查找到指定字符会返回 `-1`：

```python
test = "ucicnxznc"
v1 = test.find('c')
v2 = test.find('c',2,4)
v3 = test.find('a')
print(v1)
print(v2)
print(v3)

# 程序执行结果
1
3
-1
```

> `rfind()`类似 `find()` ,前者是从右开始查找

**index(self, sub, start=None, end=None) 和 rindex()**

该方法和 `find`方法类似，但是 `index` 有个弊端就是当未查找到指定字符后程序会报错，不建议使用。`rindex()`类似 `index()`只是从右开始查找

**format()**

该方法用于格式化输出字符串，功能丰富，例如：

```python
name = input("请输入您的姓名：")
print("Hello,{name}".format(name=name))
print("Hello,{0}".format(name))

# 程序执行结果
请输入您的姓名：abc
Hello,abc
Hello,abc
```

> 还有一种利用 `%`格式化输出字符串的方法,后续会更新....

**format_map()**

该方法和`format`方法类似，类似字典

**isalnum()**

该方法表示判断字符串是否只包含字母或者数字，返回结果为布尔值：

```python
t1 = "acxc"
t2 = "123"
t3 = "accx123"
t4 = "cxc123_"
v1 = t1.isalnum()
v2 = t2.isalnum()
v3 = t3.isalnum()
v4 = t4.isalnum()
print(v1,v2,v3,v4)

# 程序执行结果
True True True False
```

**isalpha()**

该方法表示判断字符串是否全为字母，返回结果为布尔值：

```python
test1 = "abc"
test2 = "abc123"
v1 = test1.isalpha()
v2 = test2.isalpha()
print(v1,v2)

# 程序执行结果
True False
```

**isdecimal()**、**isdigit()** 和 **isnumeric()**

该三种方法主要是判断字符串是否只包含数字，但是这三种方法也是区别的，`isdecimal()`只是判断 `0-9`普通数字,检查字符串是否只包含十进制字符，如果是返回 true，否则返回 false，`isdigit()` 不仅可以判断普通数字而且还可以判断特殊数字，例如`②` ，而 `isnumeric()`不仅可以判断普通数字和特殊数字，而且还可以判断汉子数字，例如`二`

```python
test1 = "123"
test2 = "②"
test3 = "二"
for i in test1,test2,test3:
    v1 = i.isdecimal()
    v2 = i.isdigit()
    v3 = i.isnumeric()
    print(v1,v2,v3)

# 程序执行结果
True True True
False True True
False False True
```

> 建议用的较多的是 `isdecimal()`方法，因为普通数字可以进行数值运算

**isidentifier()**

该方法用于判断字符串是否是有效的 Python 标识符，可用来判断变量名是否合法，返回值为布尔值：

```python
t1 = "test"
t2 = "123"
t3 = "abc123"
t4 = "abc_123"
t5 = "_abc123"
t6 = "123abc"
t7 = "&123b"
for i in t1,t2,t3,t4,t5,t6,t7:
    v = i.isidentifier()
    print(v)

# 程序执行结果
True
False
True
True
True
False
False
```

> Python 标识符一般由数字、字母和下划线组成且不能以数字开头

**islower()** 和 **isupper()**

上述两种方法用来判断指定字符串是否为小写和大写，返回结果为布尔值：

```python
test1 = "abc"
test2 = "ABC"
test3 = "Abc"
v1 = test1.islower()
v2 = test1.isupper()
v3 = test2.islower()
v4 = test2.isupper()
v5 = test3.islower()
v6 = test3.isupper()
print(v1,v2,v3,v4,v5,v6)

# 程序执行结果
True False False True False False
```

**isprintable()**

该方法用来判断字符串打印出来是否显示特殊字符，例如空格`\t`或者换行`\n`等字符

```python
test = "acxucxccxccc"
t = "cxc\tcxc"
v2 = test.isprintable()
v1 = t.isprintable()
print(v2,v1)

# 程序执行结果
True False
```

**isspace()**

该方法判断是否只为空格：

```python
test1 = ""
test2 = " "
v1 = test1.isspace()
v2 = test2.isspace()
print(v1,v2)

# 程序执行结果
False True
```

**title()** 和 **istitle()**

`title()`方法是将字符串转化为标题格式(首字母全大写)

`istitle()`方法是判断字符串是否为标题格式，返回值为布尔值

```python
test = "acx cxcx cxcx ef cxc is crfr"
v1 = test.title()
v2 = test.istitle()
v3 = v1.istitle()
print(v1)
print(v2)
print(v3)

# 程序执行结果
Acx Cxcx Cxcx Ef Cxc Is Crfr
False
True
```

**rjust(width[, fillchar])** 和 **ljust(width[, fillchar])**

`ljust()`返回一个原字符串左对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。

`rjust()`返回一个原字符串右对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。

```python
test = "alex"
v1 = test.ljust(20,'*')
v2 = test.rjust(20,'*')
print(v1)
print(v2)

# 程序执行结果
alex****************
****************alex
```

**strip()、lstrip() 和 rstrip()**

此三类方法主要用来去除字符串中的空格或者指定字符，`strip()`去除左右，`lstrip()`去除左边的空格或者指定字符，`rstrip()`去除右边的空格或者指定字符：

```python
## 去掉空格
test = " aalexc "
v1 = test.strip()
v2 = test.lstrip()
v3 = test.rstrip()
print(v1)
print(v2)
print(v3)

# 程序执行结果
aalexc
aalexc #右边带空格
 aalexc

## 去掉指定字符
test = "aalexc"
v2 = test.lstrip('a')
v3 = test.rstrip('c')
print(v2)
print(v3)

# 程序执行结果
lexc
aalex
```

**maketrans()和translate()**

`maketrans()`创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。两个字符串的长度必须相同，为一一对应的关系。一般与 `translate()`同时使用

```python
test = 'ABCDEFG'
valu = '1234567'
v1 = str.maketrans(test,valu)
a = "ABOFUFG"
v2 = a.translate(v1)
print(v2)

# 程序输出结果
12O6U67
```

> **注：**Python3.4已经没有string.maketrans()了，取而代之的是内建函数: bytearray.maketrans()、bytes.maketrans()、str.maketrans()

**partition()和rpartition()**

该方法用来按照指定字符分割字符串，只能将字符串分成三份，而且包含分割字符串时使用的字符，`rpartition()`表示从右开始分割

```python
test = "cxcffdfn"
v1 = test.partition('f')
v2 = test.rpartition('f')
print(v1)
print(v2)

# 程序执行结果
('cxc', 'f', 'fdfn')
('cxcffd', 'f', 'n')
```

**replace(old, new[, max])**

replace() 方法把字符串中的 old（旧字符串） 替换成 new(新字符串)，如果指定第三个参数max，则替换不超过 max 次

```python
test = "abccxcxuhv"
v1 = test.replace('c','e')
v2 = test.replace('c','e',2)
print(v1)
print(v2)

# 程序执行结果
abeexexuhv
abeexcxuhv
```

**swapcase()**

该方法用来字符串中大小写转换（小写变大写，大写变小写）

```python
test = "aBc"
v = test.swapcase()
print(v)

# 程序执行结果
AbC
```

**split()、rsplit()、splitlines()**

split(str="", num=string.count(str)

`split()`通过指定分隔符对字符串进行切片，如果参数num 有指定值，则仅分隔 num 个子字符串

```python
test = "acuhsiaufshiasfdh"
v1 = test.split('s')
v2 = test.split('s',2)
print(v1)
print(v2)

# 程序执行结果
['acuh', 'iauf', 'hia', 'fdh']
['acuh', 'iauf', 'hiasfdh']
```

`rsplit()`和 `split()` 类似，只是从右开始分割字符串

```python
test = "acuhsiaufshiasfdh"
v1 = test.split('s')
v2 = test.split('s',2)
v3 = test.rsplit('s')
v4 = test.rsplit('s',1)
print(v1)
print(v2)
print(v3)
print(v4)

# 程序执行结果
['acuh', 'iauf', 'hia', 'fdh']
['acuh', 'iauf', 'hiasfdh']
['acuh', 'iauf', 'hia', 'fdh']
['acuhsiaufshia', 'fdh']
```

`splitlines([keepends])`是按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。

```python
test = "audv\ncuxznc"
v1 = test.splitlines()
v2 = test.splitlines(True)
v3 = test.splitlines(False)
print(v1)
print(v2)
print(v3)

# 程序执行结果
['audv', 'cuxznc']
['audv\n', 'cuxznc']
['audv', 'cuxznc']
```

> 上述分割方法不带分隔符，对比 `partition()`

**zfill()**

该方法返回指定长度的字符串，原字符串右对齐，前面填充0

```python
t = "alex"
v = t.zfill(20)
print(v)

# 程序执行结果
0000000000000000alex
```











 




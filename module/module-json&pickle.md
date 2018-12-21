# json&pickle 模块

之前用 eval 内置方法可以将一个字符串转成 python 对象，不过，eval 方法是有局限性的，对于普通的数据类型，`json.loads()` 和 `eval` 都能用，但遇到特殊类型的时候，eval 就不管用了,所以 eval 的重点还是通常用来执行一个字符串表达式，并返回表达式的值。

下面有个小实例用来引入 `json.loads()`方法

```python
import json
test = "[1,2,3,4,5]"
print(test,type(test))
print(eval(test),type(eval(test)))
print(json.loads(test),type(json.loads(test)))

# 程序执行结果
[1,2,3,4,5] <class 'str'>
[1, 2, 3, 4, 5] <class 'list'>
[1, 2, 3, 4, 5] <class 'list'>
```

**序列化**

我们把对象(变量)从内存中变成可存储或传输的过程称之为序列化，在 Python 中叫 pickling ，在其他语言中也被称之为 serialization，marshalling，flattening 等等，都是一个意思。

序列化之后，就可以把序列化后的内容写入磁盘，或者通过网络传输到别的机器上。

反过来，把变量内容从序列化的对象重新读到内存里称之为反序列化，即 unpickling。

## Json 模块

如果我们要在不同的编程语言之间传递对象，就必须把对象序列化为标准格式，比如 XML，但更好的方法是序列化为 JSON，因为 JSON 表示出来就是一个字符串，可以被所有语言读取，也可以方便地存储到磁盘或者通过网络传输。JSON 不仅是标准格式，并且比 XML 更快，而且可以直接在 Web 页面中读取，非常方便。

JSON 表示的对象就是标准的 JavaScript 语言的对象，JSON 和 Python 内置的数据类型对应如下：

![JSON 和 Python 内置的数据类型对应表](https://ws1.sinaimg.cn/large/006tNbRwly1fye8lp3fo4j30wg0aemxs.jpg)

Json 模块常用的两个方法，分别是：

```python
json.dumps() # 用于将 Python 对象编码成 JSON 字符串
json.loads() # 将已编码的 JSON 字符串解码为 Python 对象
```

示例：

```python
#----------------------------序列化
import json
 
dic={'name':'alvin','age':23,'sex':'male'}
print(type(dic))    # <class 'dict'>
 
j=json.dumps(dic)
print(type(j))      # <class 'str'>
 
 
f=open('test','w')
f.write(j)          # 等价于json.dump(dic,f)
f.close()

#-----------------------------反序列化
import json
f=open('test','r')
data=json.loads(f.read())   # 等价于data=json.load(f)
```

> 需要注意的是 json 不认单引号，必须是双引号，有时候引号不显示，但其实有引号的 ''或者 ""，可以认为无论数据是怎样创建的，只要满足json格式，就可以json.loads 出来,不一定非要 dumps 的数据才能loads



## Pickle 模块

pickle 模块和 json 模块类似，不同的是 pickle 模块是将 python 对象转换成 bytes 类型或是将 bytes 类型转换成 python 对象。

pickle 模块常用的也有两个方法：

```python
pickle.dumps()  # 将 python 对象转换成 bytes 类型
pickle.loads()  # 将 bytes 类型转换成 python 对象
```

示例：

```python
##----------------------------序列化
import pickle
 
dic={'name':'alvin','age':23,'sex':'male'}
 
print(type(dic))    # <class 'dict'>
 
j=pickle.dumps(dic)
print(type(j))      # <class 'bytes'>
 
 
f=open('test','wb') # 注意是w是写入str,wb是写入bytes,j是'bytes'
f.write(j)          # 等价于pickle.dump(dic,f)
 
f.close()

#-------------------------反序列化
import pickle
f=open('test','rb')
 
data=pickle.loads(f.read()) # 等价于data=pickle.load(f)
 
 
print(data['age'])    
```

> 需要注意的是 Pickle 的问题和所有其他编程语言特有的序列化问题一样，就是它只能用于 Python，并且可能不同版本的 Python 彼此都不兼容，因此，只能用 Pickle 保存那些不重要的数据，不能成功地反序列化也没关系。


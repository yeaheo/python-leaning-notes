# 关于类

类即类别、种类，是面向对象设计最重要的概念，对象是特征与技能的结合体，而类则是一系列对象相似的特征与技能的结合体

`类`用来描述具有相同的属性和方法的对象的集合。它定义了该集合中每个对象所共有的属性和方法。对象是类的实例。

**创建类：**

使用 class 语句来创建一个新类，class 之后为类的名称并以冒号结尾:

```python
class Myclass:
    '类的帮助信息，描述类的用途'  #类文档字符串
    class_suite              # 类体
    
# 程序执行结果
<class '__main__.myclass'>
```

建议声明类的时候类名首字母大写。类的帮助信息可以通过 `ClassName.__doc__`查看。

class_suite 由类成员，方法，数据属性组成。

**实例化**

当我们调用类的时候，其实就是实例化的过程，如下：

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

class myclass:
    '类的帮助信息，描述类的用途'  #类文档字符串
    pass


print(myclass)

c1 = myclass()
print(c1)

# 程序执行结果
<class '__main__.myclass'>
<__main__.myclass object at 0x00F5F770>    # 实例化
```

在 python 2 中类分为经典类和新式类：

```python
# 经典类
class myclass:
    pass
# 新式类
class myclass(object):
    pass
```

而在 python 3 中都统一为类：

```python
class myclass:
    pass
```

**关于属性**

在类中，属性一般分为两类：

```python
1、数据属性：  就是变量
2、函数属性：  就是函数，在面向对象里称为方法
```

> 需要注意的是类和对象在访问自己属性的时候均用 `.`来访问

```python
class myclass:
    '类的帮助信息，描述类的用途'  #类文档字符串
    namea = "alex"
    def lector(name,age):
        print("%s 年龄是 %s" %(name,age))

print(myclass.namea)       # 数据属性
myclass.lector('eric',25)  # 函数属性
print(myclass.__dict__)    # 查看类的属性字典，数据属性其实是从属性字典内取值例如 myclass.__dict__['namea']

# 程序执行结果
alex
eric 年龄是 25
```

## 类的一些内置方法

类默认内置了好多方法，这里我们介绍几个：

```python
print(myclass.__name__)   ## 显示类的名称   ***
print(myclass.__doc__)    ## 显示类的doc文本内容    ***
print(myclass.__dict__)   ## 显示类的属性字典   ***
print(myclass.__base__)   ## 显示类的object
print(myclass.__bases__)  ## 显示类的object（以元组的形式显示）
print(myclass.__module__) ## 显示类的模块
print(myclass.__class__)  ## 显示type
```




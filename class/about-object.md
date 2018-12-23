# 关于对象

对象是由类实例化而来的某一个具体实例，类实例化的结果称为一个类的实例或者对象

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

class myclass:
    '类的帮助信息，描述类的用途'  #类文档字符串
    namea = "alex"
    
    def __init__(self,name,age,xingbie):
        self.name = name
        self.age = age
        self.xingbie = xingbie
# init函数不需要写 return 自动 return

    def lector(self):
        print("%s 年龄是 %s" %(slef.name,self.age))

p1 = myclass('alex',16,'male')
print(p1)
print(p1.__dict__)
print(p1.name)

# 程序执行结果
<__main__.myclass object at 0x00D1DC10>
{'name': 'alex', 'age': 16, 'xingbie': 'male'}
alex

# 实例只包含数据属性
```

>  实例只包含数据属性，不包括函数属性，函数属性是属于类的


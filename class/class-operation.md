# 类属性操作

类属性操作一般类属性的增删改查等操作，具体如下：

首先需要定义一个类;

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

class Employee:
    '所有员工的基类'
    empCount = 0

    def __init__(self, name, salary):
        self.name = name
        self.salary = salary
        Employee.empCount += 1

    def displayCount(self):
        print("Total Employee %d" % Employee.empCount)

    def displayEmployee(self):
        print("Name : ", self.name, ", Salary: ", self.salary) 
```

- empCount 变量是一个类变量，它的值将在这个类的所有实例之间共享。你可以在内部类或外部类使用 Employee.empCount 访问。
- 第一种方法__init__()方法是一种特殊的方法，被称为类的构造函数或初始化方法，当创建了这个类的实例时就会调用该方法
- self 代表类的实例，self 在定义类的方法时是必须有的，虽然在调用时不必传入相应的参数。

```python
.....
# 查看类属性
a = Employee.empCount
print(a)

# 修改类属性
b = Employee.country
print(b)
Employee.country = "USA"
d = Employee.country
print(d)

# 删除类属性
del Employee.country

# 增加类属性
Employee.location = "Beijing"
Employee.pro = "Beijing"
print(Employee.__dict__)


# 程序输出结果
0
China
USA
{'__module__': '__main__', '__doc__': '所有员工的基类', 'empCount': 0, '__init__': <function Employee.__init__ at 0x01518ED0>, 'displayCount': <function Employee.displayCount at 0x01518F18>, 'displayEmployee': <function Employee.displayEmployee at 0x01518F60>, '__dict__': <attribute '__dict__' of 'Employee' objects>, '__weakref__': <attribute '__weakref__' of 'Employee' objects>, 'location': 'Beijing', 'pro': 'Beijing'}
```

> 函数属性类似数据属性，需要重新定义函数再覆盖掉原有函数






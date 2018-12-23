# 对象和实例属性

对象和实例属性作用域相关，用 `.`的方式是一级一级找，当类中没有匹配的不再往外找，普通和类没有关系，直接往外找

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

class Employee:
    '所有员工的基类'
    empCount = 0
    country = "China"

    def __init__(self, name, salary):
        self.name = name
        self.salary = salary
        Employee.empCount += 1

    def displayCount(self):
        print("Total Employee %d" % Employee.empCount)

    def displayEmployee(self):
        print("Name : ", self.name, ", Salary: ", self.salary)


## 创建实例
p = Employee('alex','male')
print(p)
print(p.__dict__)

##
print(p.country)
p.country = "USA"
print(p.country)          # 实例的数据属性
print(Employee.country)   # 类的数据属性
```

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

country = "AAA"
class Employee:
    '所有员工的基类'
    empCount = 0
    country = "China"

    def __init__(self, name, salary):
        self.name = name
        self.salary = salary
        Employee.empCount += 1
        print('---',country)

    def displayCount(self):
        print("Total Employee %d" % Employee.empCount)

    def displayEmployee(self):
        print("Name : ", self.name, ", Salary: ", self.salary)

p1 = Employee('alex','male')
print(p1.__dict__)
print(p1.country)

# 程序输出结果
--- AAA                               # 和类没关系
{'name': 'alex', 'salary': 'male'}
China                                 # 类中定义
```


# 实例属性操作

实例属性一般也分为增删改查等操作，具体如下：

初始类：

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
```

- empCount 变量是一个类变量，它的值将在这个类的所有实例之间共享。你可以在内部类或外部类使用 Employee.empCount 访问。
- 第一种方法__init__()方法是一种特殊的方法，被称为类的构造函数或初始化方法，当创建了这个类的实例时就会调用该方法
- self 代表类的实例，self 在定义类的方法时是必须有的，虽然在调用时不必传入相应的参数。

```python
......
## 实例属性增删改查，创建实例
p = Employee('alex','male')
print(p)
print(p.__dict__)

## 查看实例属性
print(p.empCount)
print(p.country)
p.displayCount()
p.displayEmployee()

## 增加实例属性
p.namea = "hello world"
print(p.__dict__)
print(p.namea)

def test(self):
    print("test")

p.test = test
print(p.__dict__)
p.test(p)

## 删除实例属性
del p.namea
print(p.__dict__)

## 修改实例属性
p.country = "USA"
print(p.country)


# 程序输出结果
<__main__.Employee object at 0x02DEDC10>
{'name': 'alex', 'salary': 'male'}
1
China
Total Employee 1
Name :  alex , Salary:  male
{'name': 'alex', 'salary': 'male', 'namea': 'hello world'}
hello world
{'name': 'alex', 'salary': 'male', 'namea': 'hello world', 'test': <function test at 0x02DFCE40>}
test
{'name': 'alex', 'salary': 'male', 'test': <function test at 0x02DFCE40>}
USA
```


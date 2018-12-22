# xml 模块

Xml 模块是 `xml.etree.ElementTree`，常用的方法比较少，这里简单介绍几个，具体如下描述：

测试用 xml 文件：

```xml
<?xml version="1.0"?>
<data>
    <country name="Liechtenstein">
        <rank updated="yes">2</rank>
        <year>2008</year>
        <gdppc>141100</gdppc>
        <neighbor name="Austria" direction="E"/>
        <neighbor name="Switzerland" direction="W"/>
    </country>
    <country name="Singapore">
        <rank updated="yes">5</rank>
        <year>2011</year>
        <gdppc>59900</gdppc>
        <neighbor name="Malaysia" direction="N"/>
    </country>
    <country name="Panama">
        <rank updated="yes">69</rank>
        <year>2011</year>
        <gdppc>13600</gdppc>
        <neighbor name="Costa Rica" direction="W"/>
        <neighbor name="Colombia" direction="E"/>
    </country>
</data>
```

## 查看标签方法

**parse()**

该方法用来解析 `xml`格式的文件：

```python
import xml.etree.ElementTree as ET

tree = ET.parse('xmltest.xml')
print(tree)

# 程序执行结果
<xml.etree.ElementTree.ElementTree object at 0x103006c88> # 内存地址
```

**getroot()**

该方法用来获取 `xml`标签

```python
import xml.etree.ElementTree as ET

tree = ET.parse('xmltest.xml')
roottag = tree.getroot()
print(roottag)

# 程序输出结果
<Element 'data' at 0x105bb5ef8>  # 内存地址
```

**tag**

该方法用来获取标签：

```python
import xml.etree.ElementTree as ET
tree = ET.parse('xmltest.xml')
roottag = tree.getroot()
print(roottag.tag)

# 程序输出结果
data  # 顶级标签
```

获取二级标签：

```python
import xml.etree.ElementTree as ET

tree = ET.parse('xmltest.xml')
roottag = tree.getroot()

for i in roottag:
    print(i.tag)   # 获取所有二级标签

# 程序执行结果
country
country
country
```

**attrib**

该方法用来获取标签属性：

```python
import xml.etree.ElementTree as ET

tree = ET.parse('xmltest.xml')
roottag = tree.getroot()

for i in roottag:
    print(i.attrib)  # 获取标签属性
    
# 程序执行结果
{'name': 'Liechtenstein'}
{'name': 'Singapore'}
{'name': 'Panama'}
```

**text()**

该方法用来获取标签元素：

```python
import xml.etree.ElementTree as ET

tree = ET.parse('xmltest.xml')
roottag = tree.getroot()

for i in roottag:
    for j in i:
        print(j.text)  # 获取标签元素

# 程序执行结果
2
2008
141100
None
None
5
2011
59900
None
69
2011
13600
None
None
```

**iter()**

该方法用于从标签中选出某一个标签值，参数为标签名称：

```python
import xml.etree.ElementTree as ET

tree = ET.parse('xmltest.xml')
roottag = tree.getroot()

for i in roottag.iter('year'):  # 从标签中取出某个参数
    print(i.tag,i.text)

# 程序执行结果
year 2008
year 2011
year 2011
```

## 修改标签方法

将上述 xml 格式的文件的 year 标签值统一加 1：

```python
import xml.etree.ElementTree as ET

tree = ET.parse('xmltest.xml')
roottag = tree.getroot()

for node in roottag.iter('year'):
    new_year = int(node.text) + 1
    node.text = str(new_year)
    node.set('updated',"yes")   # 设置标签属性

tree.write("xmltest2.xml")  # 重新写到新文件
```

## 删除标签

将上述 xml 格式的文件 rank 参数的值大于 50 的删除：

```python
import xml.etree.ElementTree as ET

tree = ET.parse('xmltest.xml')
roottag = tree.getroot()

for i in roottag.findall('country'):   # findall/find  找标签  findall 可以找多个
    rank = int(i.find('rank').text)
    if rank > 50:
        roottag.remove(i)    # 删除标签
tree.write('xmltest3.xml')   # 重新写入文件
```

## 创建 xml 格式文件

```python
import xml.etree.ElementTree as ET

new_xml = ET.Element("namelist")
name = ET.SubElement(new_xml, "name", attrib={"enrolled": "yes"})
age = ET.SubElement(name, "age", attrib={"checked": "no"})
sex = ET.SubElement(name, "sex")
sex.text = '33'
name2 = ET.SubElement(new_xml, "name", attrib={"enrolled": "no"})
age = ET.SubElement(name2, "age")
age.text = '19'

et = ET.ElementTree(new_xml)  # 生成文档对象
et.write("test.xml", encoding="utf-8", xml_declaration=True)

ET.dump(new_xml)  # 打印生成的格式
```




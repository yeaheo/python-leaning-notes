# re 模块

```python
.   通配符
^   匹配开头
$   匹配结尾
*   匹配 0 到 无穷 次
+   匹配 1 到 无穷 次
?   匹配 0 或 1 次
{}  可以自定义匹配次数
# 例如：
# {0,}相当于 *
# {1,}相当于 +
# {0,1}相当于 ？
# {6} 匹配6次
# {1，6} 匹配 1 到 6 次
注意： 匹配规则默认是贪婪匹配，加个"?"可以改成惰性匹配，按照最小的范围进行匹配

[]   字符集，没有特殊字符,在字符集中具有特殊意义的符号 - ^ \
# - 表示范围  例如 [a-z] 表示匹配小写a到z
# ^ 表示 非   [^a-z] 表示不匹配小写a到z
# \ 表示转义

\d  [0-9]
\D  [^0-9]
\s  [\t\n\r\f\v]
\S  [^\t\n\r\f\v]
\w  [a-zA-Z0-9]
\W  [^a-zA-Z0-9]
\b  匹配一个特殊字符边界,匹配空白或者特殊字符
print(re.findall(r"I\\b","hello I am LIST"))  # 加 r 表示原生字符串，不转义
print(re.findall("c\\\\l","cufudsc\lbcbc")

| 管道符，或
() 分组
print(re.search("(?p<name>\w+)","abccdhd"))
re.search("(?p<name>\w+)","abccdhd").group("name")
search 匹配成功后不再往后匹配
返回为一个对象，取出该对象用group()


```

Re 模块常用方法：

```python
findall(),返回值为一个列表，当用到分组后，返回的是分组内的内容返回，如果要更改返回内容，可以加个`?:`调整优先级：
    print(re.findall("www\.(?:baidu|163)\.com","www.baidu.com"))
    print(re.findall("www\.(baidu|163)\.com","www.baidu.com"))
search()，返回值为一个对象 .group()
match()，返回值为一个对象，只能从开始匹配，相当于在 search 基础上加个 ^,.group()
split()，分割
sub(),替换，三（四）个参数，最后一个参数表示匹配的次数
subn(),类似sub,但是分会结果类似元祖的形式，参数为修改后的参数及匹配的次数
compile()，一个参数，(匹配规则)，返回一个对象，然后再调用findall()方法即可，不用写匹配规则，因为这些匹配规则已经编译到返回的对象中了
finditer(),类似 findall(),不同的是findall()返回的是一个列表，而 finditer()返回的是一个对象地址

```


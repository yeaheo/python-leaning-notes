# 字符串-str

字符串是以单引号`'`或双引号`"`括起来的任意文本，比如`'abc'`，`"xyz"`等等。需要注意的是，`''`或`""`本身只是一种表示方式，不是字符串的一部分，因此，字符串`'abc'`只有`a`，`b`，`c`这3个字符。如果`'`本身也是一个字符，那就可以用`""`括起来，比如`"I'm OK"`包含的字符是`I`，`'`，`m`，空格，`O`，`K`这6个字符。

其实字符串本身有许多方法，这里我只是记录了几个方便后期回来复查，具体方法如下：

**str.capitalize()**

该方法表示将字符串首字母变为大写：

```python
test = 'lvxiaoteng'
v = str.capitalize(test)
print(v)

# 程序执行结果
Lvxiaoteng
```

**str.casefold()** 和 **str.lower()**

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




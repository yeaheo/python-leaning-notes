# 布尔值-bool

布尔值就是 `True` 和 `False`

True ==> 1

False ==> 0

布尔值转换用 `bool()`

以下情况下均为 `False`，其余基本为 `True`

```python
None "" [] () {} 0 ==> False
```

```python
v1 = bool(None)
v2 = bool("")
v3 = bool([])
v4 = bool(())
v5 = bool(0)
v6 = bool({})
print(v1,v2,v3,v4,v5,v6)

# 程序执行结果
False False False False False False
```


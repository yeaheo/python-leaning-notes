# os 模块

os 模块是与操作系统交互的一个接口，该模块提供了非常丰富的方法用来处理文件和目录，具体方法如下所述：

**os.getcwd()**

该方法用于获取当前工作目录，即当前 python 脚本工作的目录路径

```python
import os
test = os.getcwd()
print(test)

# 程序输出结果
/Users/qingclass/workspace/mypy/modules
```

**os.chdir("dirname")**

 该方法用于改变当前脚本工作目录，相当于 shell 下的 `cd`

```python
import os
test = os.getcwd()
os.chdir("/Users/qingclass/workspace/")
test = os.getcwd()
print(test)

# 程序执行结果
/Users/qingclass/workspace/
```

**os.curdir()**

该方法用于返回当前目录: ('.')：

```python
import os
print(os.curdir)

# 程序执行结果
.
```

**os.pardir()**

该方法用于获取当前目录的父目录字符串名：('..')

```python
import os
print(os.pardir)

# 程序执行结果
..
```

**os.makedirs('dirname1/dirname2')**    

该方法用于生成多层递归目录：

```python
os.makedirs("./abc/test")
```

**os.removedirs('dirname1')**    

该方法用于删除目录，若目录为空，则删除，并递归到上一级目录，如若也为空，则删除，依此类推

```python
os.removedirs('./abc/test')
```

还有两种类似的方法：

```python
os.mkdir('dirname')    生成单级目录；相当于shell中mkdir dirname
os.rmdir('dirname')    删除单级空目录，若目录不为空则无法删除，报错；相当于shell中rmdir dirname
```

**os.listdir('dirname')**

该方法用于列出指定目录下的所有文件和子目录，包括隐藏文件，并以列表方式打印

```python
import os
print(os.listdir('/Users/qingclass/workspace/'))

# 程序输出结果
['abc', 'tools', '.DS_Store', 'app', 'solarized', 'blog', 'app-deployment.yaml', 'gitlab-bak', 'project', 'newblog', 'mypy', 'opentest', 'update-openssh.sh', 'open-project', 'robbyrussell.zsh-theme']
```

```python
os.remove()  删除一个文件
os.rename("oldname","newname")  重命名文件/目录

```

**os.stat('path/filename')**

该方法用于获取文件/目录信息：

```python
import os
print(os.stat("/Users/qingclass/workspace/update-openssh.sh"))
# 程序输出结果
os.stat_result(st_mode=33261, st_ino=903293, st_dev=16777220, st_nlink=1, st_uid=501, st_gid=20, st_size=4730, st_atime=1540196376, st_mtime=1540196320, st_ctime=1540196925)
```

一些方法常用，这里就简单提一下吧：

```python
os.sep        输出操作系统特定的路径分隔符，win下为"\\",Linux下为"/"
os.linesep    输出当前平台使用的行终止符，win下为"\t\n",Linux下为"\n"
os.pathsep    输出用于分割文件路径的字符串 win下为;,Linux下为:
os.name       输出字符串指示当前使用平台。win->'nt'; Linux->'posix'
os.environ    获取系统环境变量  # print(os.environ)

```

**os.system("bash command")**

该方法用于运行 shell 命令，直接显示

```python
import os
os.system('ls /opt/')

# 程序执行结果
siege-4.0.4
vagrant
```

**os.path.abspath(path)**  

该方法用于返回 path 规范化的绝对路径：

```python
import os
print(os.path.abspath('/Users/qingclass/workspace/'))

# 程序执行结果
/Users/qingclass/workspace
```

**os.path.split(path)**  

该方法用于将 path 分割成目录和文件名二元组返回，若文件名为空，则输出元组第二个元素为空字符串：

```python
import os

print(os.path.split('/Users/qingclass/workspace/update-openssh.sh'))

# 程序执行结果
('/Users/qingclass/workspace', 'update-openssh.sh')
```

**os.path.dirname(path)** 

该方法用于返回 path 的目录。其实就是 `os.path.split(path)` 的第一个元素:

```python
import os
print(os.path.dirname('/Users/qingclass/workspace/update-openssh.sh'))

# 程序执行结果
/Users/qingclass/workspace
```

**os.path.basename(path)**

 该方法用于返回 path 最后的文件名。如果 path 以／或 \ 结尾，那么就会返回空值。即 `os.path.split(path)` 的第二个元素:

```python
import os
print(os.path.basename('/Users/qingclass/workspace/update-openssh.sh'))

# 程序执行结果
update-openssh.sh
```

其他一些判断目录或者文件是否存在的方法如下描述。这里不再赘述：

```python
os.path.exists(path)  如果path存在，返回True；如果path不存在，返回False
os.path.isabs(path)   如果path是绝对路径，返回True
os.path.isfile(path)  如果path是一个存在的文件，返回True。否则返回False
os.path.isdir(path)   如果path是一个存在的目录，则返回True。否则返回False
os.path.join(path1[, path2[, ...]])  将多个路径组合后返回，第一个绝对路径之前的参数将被忽略
```

**os.path.getatime(path)**

 该方法用于返回 path 所指向的文件或者目录的最后存取时间,默认返回的是时间戳形式的时间，我们可以将其转换为字符串类型的时间：

```python
import os
import time
test = os.path.getatime('/Users/qingclass/workspace/update-openssh.sh')
abc = time.localtime(test)
print(time.strftime("%Y-%m-%d %X",abc))

# 程序输出结果
2018-10-22 16:19:36
```

**os.path.getmtime(path)** 

 该方法用于返回 path 所指向的文件或者目录的最后修改时间，类似 `os.path.getatime(path)`方法，也是返回时间戳格式的时间，我们可以将其转化为字符串时间

```python
import time 
import os

abc_time = os.path.getmtime('/Users/qingclass/workspace/update-openssh.sh')
d_time = time.localtime(abc_time)
print(time.strftime("%Y-%m-%d %X",d_time))

# 程序输出结果
2018-10-22 16:18:40
```


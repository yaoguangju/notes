| 问题 | 地址 |
| ---- | ---- |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |

##### 字符串删除多余字符的方法

```
' x y z '.replace(' ', '')
return 'xyz'
```

##### 获取当前的路径

```
import os
cwpath=os.getcwd()
print(cwpath)
```

##### 目录是否存在的方法主要利用os.path.exists(path)来判断，返回一个bool值

```
import os
path=r'D:\Python Mat\codes\Data Learning\Python基础代码'
print(os.path.exists(path))
```

##### 如何创建一个绝对路径文件夹（其父目录也会创建）

```
import os
path=r'D:\Python Mat\codes\Data Learning\1\Python练习'
os.makedirs(path)
```

##### 如何创建一个相对路径文件夹(这里先将一个路径分隔符的概念)

```
由于在Windows和Linux、Mac下路径分隔用的不同的符号，windows下用，linux用/

所以为了写的代码能在多系统上使用，我们尽量不要直接指定\或者/来链接路径

python中os.path常用模块

os.path.sep:#路径分隔符
os.path.altsep: #根目录
os.path.curdir:#当前目录，其实就是一个.。
os.path.pardir：#父目录，其实是两个.。
os.path.abspath(path)：#绝对路径
os.path.join(): #常用来链接路径，这个才是最重要的方法。
os.path.split(path): #把path分为目录和文件两个部分，以列表返回

假如我们要在当前目录下创建一个文件夹，名字随便起吧，比如是'name'。
import os
curPath=os.getcwd()
tempPath='name'
targetPath=curPath+os.path.sep+tempPath
if not os.path.exists(targetPath):
    os.makedirs(targetPath)
else:
    print('路径已经存在！')
```

##### 正则表达式匹配中文

```
[\u4e00-\u9fa5]{2,20}     匹配2到20个中文字符.
[\s]     匹配空格
```

##### range实例

```
>>> range(10)        # 从 0 开始到 10
    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> range(1, 11)     # 从 1 开始到 11
    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> range(0, 30, 5)  # 步长为 5
    [0, 5, 10, 15, 20, 25]
>>> range(0, 10, 3)  # 步长为 3
    [0, 3, 6, 9]
>>> range(0, -10, -1) # 负数
    [0, -1, -2, -3, -4, -5, -6, -7, -8, -9]
>>> range(0)
    []
>>> range(1, 0)
    []      

>>>x = 'runoob'
>>> for i in range(len(x)) :
        print(x[i])
    r
    u
    n
    o
    o
    b
```




[返回目录](ch0.md)  
[返回本书文章列表](../../../booklist/python/ch1.md)  

# 《看漫画学Python》学习笔记（一）——编程知识基础

    本文内容是基于《看漫画学Python：有趣、有料、好玩、好用（全彩版）》的学习笔记

## 文章导图

<!-- https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/booknote/python/ch1/ch1-1.png -->

![文章导图](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/booknote/python/CAT1/ch1/ch1-1.png "文章导图")

## 目录

1. [标识符](#1)
2. [关键字](#2)
3. [变量](#3)
4. [bug](#4)
5. [语句](#5)
6. [代码注释](#6)
7. [模块](#7)
    1. [import 导入模块](#7-1)
    2. [from … import 导入模块](#7-2)

## 1. 标识符<a name="1"></a>

标识符是可以自定义名称的变量、函数、属性、类、模块等代码元素，但需要遵循一定的命名规则。  
那么命名规则是什么呢？  
具体命名规则如下：  
1. 区分大小写
2. 首字符可以是下划线和字母，不能是数字
3. 除首字符外的其他字符必须是下划线、数字和字母其一
4. 关键字不能作为标识符
5. 不使用Python的内置函数作为标识符

## 2. 关键字<a name="2"></a>

具有特殊含义由语言本身定义好的代码元素  
Python中的关键字如下表所示：  

| True  | False  | None     | and   | as     | assert   |
|:-----:|:------:|:--------:|:-----:|:------:|:--------:|
| break | class  | continue | def   | del    | elif     |
| else  | except | finally  | for   | from   | global   |
| if    | import | in       | is    | lambda | nonlocal |
| not   | or     | pass     | raise | return | try      |
| while | with   | yield    |       |        |          |

## 3. 变量<a name="3"></a>

变量赋值的同时进行声明，变量数据类型为赋值数据的类型，变量在赋值后仍可接收其他类型的数据

示例代码如下：  

```python
num = 10
num = 'Hello World!'
```

## 4. bug<a name="4"></a>

程序中的缺陷、漏洞、错误等。

## 5. 语句<a name="5"></a>

一行代码表示一条语句，语句结束时一般不加分号。

示例代码如下：

```python
print('Hello World')
```

## 6. 代码注释<a name="6"></a>

当井号（\#）位于语句开头，后面的便是注释内容，井号和注释内容之间有一个空格

示例代码如下：

```python
# 这是一个代码注释
```

## 7. 模块<a name="7"></a>

保存代码的最小单位，即一个文件，模块中可以声明变量、函数、属性和类等代码元素

### 1. import 导入模块<a name="7-1"></a>

使用`import`可以导入模块内的所有代码元素，使用模块内的代码元素时需要加模块名前缀亦或别名

示例代码如下：

```python
# module.py
def sayHello():
    print('Hrllo World!')

# main.py 加模块名前缀使用模块内代码元素
import module

module.sayHello()

# main.py 加别名前缀使用模块内代码元素
import module as mod

mod.sayHello()
```

### 2. from … import 导入模块<a name="7-2"></a>

使用`from ... import ...`可以导入指定的代码元素，可以给导入的元素一个别名，可以通过别名或代码元素名称直接使用这些代码元素

```python
# module.py
def sayHello():
    print('Hello World')

# main.py 导入指定的代码元素
from module import sayHello

sayHello()

# main.py 导入指定的代码元素并给予别名
from module import sayHello as hello

hello()
```

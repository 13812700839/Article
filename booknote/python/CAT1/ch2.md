[返回目录](ch0.md)  
[返回本书文章列表](../../../booklist/python/ch1.md) 

# 《看漫画学Python》学习笔记（二）——数据类型

    本文内容是基于《看漫画学Python：有趣、有料、好玩、好用（全彩版）》的学习笔记

## 文章导图

![文章导图](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/booknote/python/CAT1/ch2/ch2-1.png "文章导图")

## 目录

1. [什么是数据类型](#1)
2. [整数类型](#2)
3. [浮点类型](#3)
4. [复数类型](#4)
5. [布尔类型](#5)
6. [数字类型的转换](#6)
    1. [隐式类型的转换](#6-1)
    2. [显示类型的转换](#6-2)

## 1. 什么是数据类型<a name="1"></a>

所有数据类型都是类，数据值是数据类型的实例。  
Python主要的内置数据类型有6种：数字、字符串、列表、元组、集合和字典。其中，列表、元组、集合和字典均能容纳多个数据，统称为容器类型的数据。  
数字类型有四种，整数类型、浮点类型、复数类型和布尔类型，其中，布尔类型也是一种整数类型。  

## 2. 整数类型<a name="2"></a>

`int`型为整数类型，整数类型范围大。

示例代码如下：

```python
num = 100
print(num)
# 100
print(type(num))
# <class 'int'>
print(0B10)
print(0b10)
# 以上两个结果一致
# 2
print(0O10)
print(0o10)
# 以上两个结果一致
# 8
print(0X10)
print(0x10)
# 以上两个结果一致
# 16
```

## 3. 浮点类型<a name="3"></a>

`float`型为浮点类型，仅支持双精度浮点类型。

示例代码如下：

```python
    num = 3.14
    print(num)
    # 3.14
    print(type(num))
    # <class 'float'>
    print(314e-2)
    # 3.14
    print(0.314e1)
    # 3.14
```

## 4. 复数类型<a name="4"></a>

数学中的实数分为整数和浮点数，与之对应的是复数在数学中的表示为$a+bi$，其中a为实部，b为虚部，i为虚数单位。

示例代码如下：

```python
num = 1 + 2j
print(num)
# 1 + 2j
print(type(num))
# <class 'complex'>'
print(num + num)
# 2 + 4j
print(num * 2)
# 2 + 4j
```

## 5. 布尔类型<a name="5"></a>

`bool`型为布尔类型，`bool`的父类是`int`，只有两个值`True`和`False`。

示例代码如下：

```python
print(bool(0))
# False
print(bool(1))
# True
print(bool(10))
# True
print(bool(''))
print(bool(' '))
print(bool([]))
print(bool({}))
# 以上四个结果一致
# False
```

## 6. 数字类型的转换<a name="6"></a>

布尔可以由数字类型的数据转换而来，数字类型之间也可以相互转换，数字类型中的整数类型、浮点类型和布尔类型可以相互进行转换，其中转换方式分为显示类型和隐式类型的转换。

### 1. 隐式类型的转换<a name="6-1"></a>

当不同数字类型进行数学运算时，会触发隐式类型的转换。

转换方式如下表所示：

| 操作数1类型    | 操作数2类型 | 转换后类型 |
|:---------:|:------:|:-----:|
| 布尔类型      | 整数类型   | 整数类型  |
| 布尔类型、整数类型 | 浮点类型   | 浮点类型  |
  
示例代码如下：

```python
# 整数类型和布尔类型相加
num = 10 + True
print(num)
# 11
print(type(num))
# <class 'int'>

# 整数类型和浮点类型相加
num = 10 + 3.14
print(num)
# 13.14
print(type(num))
# <class 'float'>

# 整数类型、浮点类型和布尔类型相加
num = 10 + 3.14 + False
print(num)
# 13.14
print(type(num))
# <class 'float'>
```

### 2. 显示类型的转换<a name="6-2"></a>

在数字类型中，整数类型、浮点类型和布尔类型均有自己的转换函数，如：`int()`、`float()`和`bool()`函数。

示例代码如下：

```python
# 布尔类型转换成整数类型
print(int(False))
# 0
print(int(True))
# 1

# 浮点类型转换成整数类型
print(int(3.14))
# 3

# 布尔类型转换成浮点类型
print(float(False))
# 0.0
print(float(True))
# 1.0

# 整数类型转换成浮点类型
print(float(10))
# 10.0

# 整数类型转换成布尔类型
print(bool(0))
# False
print(bool(1))
# True
print(bool(10))
# True

# 浮点类型转换成布尔类型
print(bool(0.0))
# False
print(bool(1.0))
# True
print(bool(3.14))
# True
```

    本文于2021年07月17日在简书发布 [文章地址](https://www.jianshu.com/p/cd319682bd8d)
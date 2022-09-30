[返回目录](ch0.md)  
[返回本书文章列表](../../../booklist/python/ch1.md) 

# 《看漫画学Python》学习笔记（四）——程序流程控制

    本文内容是基于《看漫画学Python：有趣、有料、好玩、好用（全彩版）》的学习笔记

## 文章导图

![文章导图](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/booknote/python/CAT1/ch4/ch4-1.png "文章导图")

## 目录

1. [分支语句](#1)
    1. [if 结构](#1-1)
    2. [if-else 结构](#1-2)
    3. [if-elif-else 结构](#1-3)
2. [循环语句](#2)
    1. [while 语句](#2-1)
    2. [for 语句](#2-2)
3. [跳转语句](#3) 
    1. [break 语句](#3-1)
    2. [continue 语句](#3-2)
4. [动动手——计算水仙花数](#4)

## 1. 分支语句<a name="1"></a>

由于Python的设计理念是简单，所以Python不支持`switch`语句，多分支功能是通过`if-elif-else`实现

### 1. if 语句<a name="1-1"></a>

语法结构如下:

```python
if 判断条件:
    语句组
```

示例代码:

```python
score = int(input('请输入分数; '))

if score >= 60:
    print('合格')
if score < 60:
    print('不合格')
```

### 2. if-else 语句<a name="1-2"></a>

语法结构如下:

```python
if 判断条件:
    语句组1
else:
    语句组2
```

示例代码:

```python
score = int(input('请输入分数: '))

if score >= 60:
    print('合格')
else:
    print('不合格')
```

### 3. if-elif-else 语句<a name="1-3"></a>

语法结构如下:

```python
if 判断条件1:
    语句组1
elif 判断条件2:
    语句组2
elif 判断条件3:
    语句组3
...
elif 判断条件n:
    语句组n
else:
    语句组n+1
```

示例代码:

```python
score = int(input('请输入分数: '))

if score >= 90:
    print('优秀')
elif score >= 80:
    print('良好')
elif score >= 60:
    print('及格')
else:
    print('不及格')
```

## 2. 循环语句<a name="2"></a>

Python支持的循环语句有：`while`和`for`语句

### 1. while 语句<a name="2-1"></a>

语法结构如下:

```python
while 循环条件:
    循环体语句组
[else:
    语句组]
```

**注意：else 子句是可选部分，else 子句仅当 while 循环未中断时执行**

示例代码:

```python
i = 0
sum = 1

while i < 11:
    sum += i
    i += 1
else:
    print('1 到 10的和:', sum)
```

### 2. for 语句<a name="2-2"></a>

语法结构如下:

```python
for 循环变量 in 可迭代对象:
    循环体语句组
[else:
    语句组]
```

**注意：**
1. 可迭代对象包括：字符串、列表、元组、集合和字典等
1. else 子句是可选部分，else 子句仅当 for 循环未中断时执行

示例代码:

```python
sum = 0

for num in range(11):
    sum += num
else:
    print('1 到 10 的和:', sum)
```

## 3. 跳转语句（循环体）<a name="3"></a>

Python 中的跳转语句有：`break`和`continue`语句。

### 1. break 语句<a name="3-1"></a>

`break`语句用于强行退出循环体，不再执行循环体中剩余语句。

示例代码:

```python
# while 循环中使用 break
num = 1

while num < 11:
    if num == 6:
        break
    print(num)
    num += 1
    
# for 循环中使用 break
for num in range(1, 11):
    if num == 6:
        break
    print(num)
```

### 2. continue 语句<a name="3-2"></a>

`continue`语句用于结束本次循环，跳过循环体中尚未执行的语句，直接进行循环条件判断是否继续循环

```python
# while 循环中使用 continue
num = 1

while num < 11:
    if num % 2 == 0:
        num += 1
        continue
    print(num)
    num += 1
    
# for 循环中使用 continue
for num in range(1, 11):
    if num % 2 == 0:
        continue
    print(num)
```

## 4. 动动手——计算水仙花数<a name="4"></a>

题目要求：通过循环计算水仙花数，分别使用`while`和`for`语句实现

*提示：水仙花数是一个三位数，三位数各位的立方之和等于三位数本身*

示例代码:

```python
# 使用 while 语句实现
sum = 0
num = 100
num1 = 0
num2 = 0
num3 = 0

while num < 1000:
    num1 = num // 100
    num2 = (num % 100) // 10
    num3 = num % 10
    sum = num1 ** 3 + num2 ** 3 + num3 ** 3
    if sum == num:
        print(num)
    num += 1
        
# 使用 for 语句实现
sum = 0
num1 = 0
num2 = 0
num3 = 0

for num in range(100, 1000):
    num1 = num // 100
    num2 = (num % 100) // 10
    num3 = num % 10
    sum = num1 ** 3 + num2 ** 3 + num3 ** 3
    if sum == num:
        print(num)
```

    本文于2022年09月30日在简书发布 [文章地址](https://www.jianshu.com/p/0c0c5e38beb6)
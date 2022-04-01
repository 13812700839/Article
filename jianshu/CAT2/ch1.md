[返回目录](ch0.md)

# MongoDB安装配置（ZIP版）

## 目录

[一、 准备工作](#一、 准备工作)  
[二、 文件配置与安装](#二、 文件配置与安装)  
    [1. 文件配置](#1. 文件配置)  
    [2. 安装](#2. 安装)  
[三、 运行测试](#三、 运行测试)  

## 一、 准备工作

从MongoDB官网下载MongoDB的ZIP安装包

官网链接：[https://www.mongodb.com/try/download/community](https://www.mongodb.com/try/download/community)

选择MongoDB Community Server，选择对应版本、平台

![image.png](https://upload-images.jianshu.io/upload_images/23708684-9a679af8936a2636.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

下载完成后解压到自己的路径

## 二、 文件配置与安装

### 1. 文件配置

进入解压后的文件夹，新建data和log文件夹，并在log文件夹下，新建mongo.log空文件

新建mongo.conf文件与bin文件夹同级

mongo.conf写入以下内容

```
# 数据库路径
dbpath=E:\other_dev\mongodb\data  

# 日志输出文件路径
logpath=E:\other_dev\mongodb\logs\mongo.log  

# 错误日志采用追加模式
logappend=true  

# 启用日志文件，默认启用 
journal=true

# 这个选项可以过滤掉一些无用的日志信息，若需要调试使用请设置为false  
quiet=true

# 端口号 默认为27017
port=27017
```

**注：dbpath和logpath根据自己的具体路径进行修改**

### 2. 安装

从bin文件夹下进入命令行执行

```bash
mongod --config "E:\other_dev\mongodb\mongo.conf"
```

**注：引号内的路径换成刚刚配置文件的路径**

执行后没有任何反应，则关掉该窗口

## 三、 运行测试

从bin文件夹下进入命令行执行

```bash
mongod --dbpath E:\other_dev\mongodb\data
```

**注：引号内的路径换成自己存放数据库的路径**

启动完成后，不要关掉该窗口，重新从bin文件夹下进入命令行执行

```bash
mongo
```

进入mongo命令行模式

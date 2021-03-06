[返回目录](ch0.md)

# NodeJS安装配置（ZIP版）

## 目录

1. [下载NodeJS的ZIP安装包](#1)  
2. [配置和安装](#配置和安装)  
    1. [配置node的缓存路径和全模块路径](#2-1)  
    2. [配置环境变量](#2-2)  
    3. [安装全模块](#2-3)  
3. [测试运行](#测试运行)  

## 一、下载NodeJS的ZIP安装包<a name="1"></a>

根据系统版本去NodeJS官网下载ZIP安装包

NodeJS官网：[https://nodejs.org/en/](https://nodejs.org/en/)

下载完成，解压到指定路径

## 二、配置和安装<a name="配置和安装"></a>

### 1. 配置node的缓存路径和全模块路径<a name="2-1"></a>

在node安装目录下新建node_cache和node_global两个文件夹

输入以下命令

```bash
npm config set prefix "D:\project\tools\node-v14.16.1-win-x64\node_global"
npm config set cache "D:\project\tools\node-v14.16.1-win-x64\node_cache"
```

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch2/ch2-1.png)


**注意：引号内的路径根据自己的具体路径进行修改**

### 2. 配置环境变量<a name="2-2"></a>

创建环境变量NODE，node的安装路径

在Path中添加%NODE%，%NODE%\node_global

检查node版本，输入命令node –v

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch2/ch2-2.png)


### 3. 安装全模块<a name="2-3"></a>

输入命令npm install express –g

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch2/ch2-3.png)


## 三、测试运行<a name="测试运行"></a>

创建一个项目进行测试

输入命令express –t ejs demo

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch2/ch2-4.png)


安装依赖，运行项目

输入命令cd demo，npm install，npm start

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch2/ch2-5.png)

    本文于2021年06月24日在简书发布 [文章地址](https://www.jianshu.com/p/e3e000c67c81)  
    本文于2021年07月19日在知乎发布 [文章地址](https://zhuanlan.zhihu.com/p/389704886)  
    本文于2021年09月15日在CSDN发布 [文章地址](https://blog.csdn.net/qq_46106320/article/details/120306455)
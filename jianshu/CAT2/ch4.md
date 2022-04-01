[返回目录](ch0.md)

# Erlang和RabbitMQ（ZIP版）安装配置

## 目录

[一、下载Erlang和RabbitMQ安装包](#一、下载Erlang和RabbitMQ安装包)  
[二、Erlang安装配置](#二、Erlang安装配置)  
    [1. 安装](#1. 安装)  
    [2. 配置](#2. 配置)  
[三、RabbitMQ安装配置](#三、RabbitMQ安装配置)  
    [1. 配置](#1. 配置)  
    [2. 测试运行](#2. 测试运行)  

## 一、下载Erlang和RabbitMQ安装包

在Erlang官网和RabbitMQ官网，根据系统版本下载Erlang和RabbitMQ安装包

Erlang官网：[https://www.erlang.org](https://www.erlang.org)

RabbitMQ官网：[http://www.rabbitmq.com](http://www.rabbitmq.com)

RabbitMQ压缩包下载地址：[https://www.rabbitmq.com/install-windows-manual.html](https://www.rabbitmq.com/install-windows-manual.html)

RabbitMQ压缩包下载后解压到指定目录下

## 二、Erlang安装配置

### 1. 安装

双击运行exe文件，指定安装路径，等待安装完成

### 2. 配置

创建环境变量ERLANG_HOME，erl的安装路径

在Path中添加%ERLANG_HOME%\bin

打开命令行，输入erl

https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/jianshu/CAT2/ch4/ch4-1.png

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch4/ch4-1.png)

Erlang配置完成

## 三、RabbitMQ安装配置

### 1. 配置

创建环境变量RABBITMQ_SERVER，rabbitMQ的安装目录

在Path中添加%RABBITMQ_SERVER%\sbin

打开命令行输入rabbitmqctl status

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch4/ch4-2.png)


说明rabbitMQ未启动

安装插件，输入命令rabbitmq-plugins.bat enable rabbitmq_management

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch4/ch4-3.png)


出现该界面则安装成功

若出现问题如下

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch4/ch4-4.png)


解决方法： 将 C:\Users\Lenovo\.erlang.cookie 同步至

C:\Windows\System32\config\systemprofile\.erlang.cookie 

同时删除：C:\Users\Lenovo\AppData\Roaming\RabbitMQ目录

### 2. 测试运行

输入命令rabbitmq-server.bat

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch4/ch4-5.png)


rabbitmq启动成功，浏览器中[http://localhost:15672](http://localhost:15672/)进行访问

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch4/ch4-6.png)


输入用户名：guest，密码：guest进入控制台

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch4/ch4-7.png)


输入命令rabbitmqctl status

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch4/ch4-8.png)


RabbitMQ部署完成

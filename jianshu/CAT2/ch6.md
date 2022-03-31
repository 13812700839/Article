[返回目录](ch0.md)

# Redis安装配置（ZIP版）

## 一、下载Redis安装包

根据系统版本下载Redis安装包

Linux版本下载地址：[https://redis.io/download](https://redis.io/download)

Windows版本下载地址：[https://github.com/microsoftarchive/redis/releases](https://github.com/microsoftarchive/redis/releases)

本文以Windows为例，下载完成后解压到自己的路径

## 二、文件配置与安装

### 1. 临时服务安装

进入Redis解压后的目录，并在该目录下启动命令行，输入以下命令

```bash
redis-server.exe redis.windows.conf
```

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch6/ch6-1.png)


打开Redis解压后的目录中的redis-cli.exe，运行redis客户端，上一个窗口不能关闭

![image.png](https://cdn.jsdelivr.net/gh/13812700839/MyImageBed/article/jianshu/CAT2/ch6/ch6-2.png)


使用临时服务安装，不会出现在Windows服务中

### 2. 默认服务安装

进入Redis解压后的目录，并在该目录下启动命令行，输入以下命令

```bash
redis-server.exe --service-install redis.windows.conf --loglevel verbose
```

**注：一定要把临时服务关闭，否则安装不上**

启动/暂停/卸载服务

```bash
# 启动
redis-server.exe --service-start
# 暂停
redis-server.exe --service-stop
# 卸载
redis-server.exe --service-uninstall
```

使用默认服务安装，会出现在Windows服务中

### 3. 自定义服务安装

进入Redis解压后的目录，并在该目录下启动命令行，输入以下命令

```bash
redis-server.exe --service-install redis.windows.conf --Service-name RedisServer1 --loglevel verbose
```

启动/暂停/卸载服务

```bash
# 启动
redis-server.exe --service-start --Service-name RedisServer1
# 暂停
redis-server.exe --service-stop --Service-name RedisServer1
#  卸载
redis-server.exe --service-uninstall --Service-name RedisServer1
```

使用自定义服务安装，可以重命名服务名并会出现在Windows服务中

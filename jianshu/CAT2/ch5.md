[返回目录](ch0.md)

# Windows下python虚拟环境中编译安装NovalIDE

本文为本人编译打包 NovalIDE 过程的记录，以防忘记

## 目录

1. [ 源码编译步骤](#1)  
    1. [克隆 NovalIDE 项目](#1-1)  
    2. [安装 pipenv 虚拟环境管理](#1-2)  
    3. [新建文件夹，在文件夹内进入命令行安装虚拟环境](#1-3)  
    4. [虚拟环境安装相应开发依赖](#1-4)  
    5. [进入虚拟环境](#1-5)  
    6. [进入到 NovalIDE 文件夹，运行 NovalIDE.py](#1-6)  
    7. [打包成 exe 文件](#1-7)  
2. [编译过程中遇到的问题](#2)  

## 1. 源码编译步骤<a name="1"></a>

### 1.1 克隆 NovalIDE 项目<a name="1-1"></a>

```bash
# dev 分支下的文件
git clone https://gitee.com/wekay/NovalIDE.git
```

### 1.2 安装 pipenv 虚拟环境管理<a name="1-2"></a>

```bash
pip install pipenv
```

### 1.3 新建文件夹，在文件夹内进入命令行安装虚拟环境<a name="1-3"></a>

```bash
# 本文安装虚拟环境的 python 版本为3.8
pipenv install --python 3.8
```

### 1.4 虚拟环境安装相应开发依赖<a name="1-4"></a>

```bash
pipenv install pywin32 --dev
pipenv install pyinstaller --dev
pipenv install psutil --dev
pipenv install watchdog --dev
pipenv install chardet --dev
pipenv install pyperclip --dev
pipenv install wmi --dev
pipenv install requests --dev
pipenv install pillow --dev
pipenv install six --dev
```

### 1.5 进入虚拟环境<a name="1-5"></a>

从该步骤进入虚拟环境开始，后面步骤均在虚拟环境中完成

```bash
pipenv shell
```

### 1.6 进入到 NovalIDE 文件夹，运行 NovalIDE.py<a name="1-6"></a>

```bash
cd NovalIDE
 
python NovalIDE.py
```

### 1.7 打包成 exe 文件<a name="1-7"></a>

```bash
pyinstaller pyinstaller.novalide.python.spec
```

## 2. 编译过程中遇到的问题<a name="2"></a>

*   **AttributeError: module 'time' has no attribute 'clock'**

由于我使用的是Python3.8版本的，NovalIDE源码中有使用time.clock()，Python3.8 不再支持 time.clock()，可将 time.clock() 替换成 time.perf_counter()

```python
# noval/util/utils.py, line 294, line 296
time.clock() -> time.perf_counter()
```

*   **PermissionError: [Errno 13] Permission denied**

我打包时出现了这个问题是因为我后台运行了360程序，退出再重新运行一遍就可以打包成功了

*   **ModuleNotFoundError: No module named 'distutils.version'**

运行打包好的exe文件，出现该错误，是因为使用了 `from distutils.version import ...`，所以没有将 distutils.version 依赖打包

在spec中的 hiddenimports 添加 distutils.version ，重新打包问题解决

```
a = Analysis(['NovalIDE.py'],
      pathex=['./'],
      binaries=[],
      datas=datas,
      hiddenimports=['noval.util.downutils','noval.python.pyeditor','noval.syntax.pat','site','noval.running','noval.shell','noval.roughparse','distutils.version'],
      hookspath=[],
      runtime_hooks=[],
      excludes=['noval.util.command'],
      win_no_prefer_redirects=False,
      win_private_assemblies=False,
      cipher=block_cipher,
      noarchive=False)
```

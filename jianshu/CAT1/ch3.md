[返回目录](ch0.md)

# Linux中Git学习笔记（三）

## 目录

[忽略文件](#忽略文件)  
[基于远程分支origin创建一个mywork分支](#基于远程分支origin创建一个mywork分支)  
[使mywork分支历史看起来没有任何合并](#使mywork分支历史看起来没有任何合并)  
[git rebase遇到冲突，git add命令解决完后可直接执行](#git rebase遇到冲突，git add命令解决完后可直接执行)  
[git索引](#git索引)  
[修复工作](#修复工作)  
[返回原工作状态](#返回原工作状态)  
[显示储存队列](#显示储存队列)  
[使用某个储存](#使用某个储存)  
[清空储存列表](#清空储存列表)  

## 忽略文件
可以在顶层工作目录中添加一个叫 .gitignore 的文件，来告诉 Git 系统要忽略掉哪些文件，下面是文件内容的示例。  
以'#' 开始的行，被视为注释。忽略掉所有文件名是 foo.txt 的文件，.gitignore 的文件内容为：  
```bash
foo.txt
# 忽略所有生成的 html 文件：
*.html
# 如果 foo.html 这个文件不能忽略，可以写个例外：
!foo.html
# 忽略所有 .o 和 .a 文件：
*.[oa]
```
## 基于远程分支origin创建一个mywork分支
```bash
git checkout -b mywork origin
```
## 使mywork分支历史看起来没有任何合并
```bash
git checkout mywork
git rebase origin
```
## git rebase遇到冲突，git add命令解决完后可直接执行
```bash
git rebase --continue
# 中止操作
git rebase --abrot
```
## git索引
```bash
git add -i
```
当你正在做一项复杂的工作时， 发现了一个和当前工作不相关但是又很讨厌的 bug. 你这时想先修复 bug 再做手头的工作， 那么就可以用 git stash 来保存当前的工作状态， 等你修复完 bug 后，执行反储藏（unstash）操作就可以回到之前的工作里。
```bash
git stash save "work in progress for foo feature"
```
## 修复工作
```bash
git commit -a -m "blorpl: typofix"
```
## 返回原工作状态
```bash
git stash apply
```
## 显示储存队列
```bash
git stash list
```
## 使用某个储存
```bash
git stash apply stash@{标号}
```
## 清空储存列表
```bash
git stash clear
```

    本文于2020年07月25日在简书发布 [文章地址](http://www.jianshu.com/p/8a4239e77370)
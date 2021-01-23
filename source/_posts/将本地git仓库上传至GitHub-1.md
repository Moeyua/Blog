---
title: 将本地git仓库上传至GitHub
date: 2021-01-21 16:38:11
tags:
cover_image: 
    - "https://i.loli.net/2021/01/21/RXGWbrCUaLINp9J.png"
---
# 将本地git仓库上传至GitHub

> 第一次通过git上传文件至GitHub，之前一直采用在线提交甚至直接修改代码的的方式来进行提交，直到今天需要将一个完整的项目提交到GitHub才发现文件夹无法直接提交，所以决定换git来提交，折腾了一中午，做一个记录
# 初次上传至GitHub

- 打开GitBash并且将目录切换至要上传的文件夹下
- 首先初始化目录

```powershell
$ git init
```

- 添加文件夹下的所有文件

```powershell
$ git add .
```

- 提交并备注信息

```powershell
$ git commit -m "备注信息"
```

- 打开GitHub仓库，点击Clone or download复制下面的仓库地址，然后回到GitBash执行以下指令来连接到远程仓库

```powershell
$ git remote add origin https://github.com/Moeyua/Moeyua.github.io.git
```

- 执行以下指令来将文件提交到远程仓库

```powershell
$ git push -u origin master
```

这个过程中可能会出现error，但我们可以通过先执行git put命令
然后再输入git push -u origin master -f来解决

- 刷新远程仓库即可看到上传成功的文件

# 后期更新仓库文件

- 首先仍然在GitBash中打开文件目录，然后输入以下指令

```powershell
$ git status
```

- 这时便能看到有修改过的文件列表，接着输入以下指令来上传所有修改

```powershell
$ git add -A
```

- 提交并备注信息，注释表示此次提交为更新

```powershell
$ git commit -a -m "uppdate"
```

- 最后执行指令将文件提交到远程仓库

```powershell
$ git push origin master -f
```

更新时并不需要写 -u 命令
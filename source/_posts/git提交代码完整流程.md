---
title: git提交代码完整流程
author: 戴昌益
date: 2024-07-03
tags: [git]
categories: 技
---

1、先拉代码

```
git pull
```

2、修改代码文件

随时枪git status查看情况

3、把更改的代码暂存起来

```
# 暂存所有更改
git add .
# 暂存指定文件
git add temp.text
# 取消暂存 可结合git status
git reset HEAD <file>
```

4、提交暂存文件到本地

```
git commit -m '说明'
```

5、上传到远程合并代码

```
git push <远程主机名> <本地分支名>:<远程分支名>
例如：git push origin master：master
```

6、配置不行需要使用token上传

1）生成token，已经生成了就不用管。

在github页面的个人主页setting-Develper settings中查看或生成token

我这里用的经典token

2）输入密码时候输入token即可。或者修改项目url为https://token@github.com/username/repo.git

使用

```
git remote set-url origin https：………………修改
```


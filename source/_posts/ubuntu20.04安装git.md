---
title: ubuntu20.04安装git
author: 戴昌益
date: 2024-7-3 15:52:07
tags: [博客部署安装]
categories: 技
---

# ubuntu20.04安装git

### 步骤01：更新软件包

执行下面提到的命令来更新 APT：

```undefined
sudo apt update
```

执行下面提到的命令来升级 apt：

```undefined
sudo apt upgrade
```

升级开始前，系统会询问您是否要继续，然后按“y”表示是。

## 第2步：安装GIT

Git实用程序包在ubuntu的软件源中提供，可以通过APT安装。只需输入以下命令即可安装Git。

```undefined
sudo apt install git
```

Git 需要安装 sudo 权限，因此输入密码然后按“y”继续安装。

## 步骤3：检查已安装的GIT版本



安装 Git 后，您可以使用屏幕截图中的以下命令检查其验证。

```sql
git --version
```

# 拉取项目文件

```
git clone https://github.com/dailaoda45/dailaoda45.github.io.git
```

## 配置 Git

可以使用终端或命令行窗口来配置 Git。它需要一个用户名，充当绑定名称和电子邮件地址。

进入git目录

### 第1步：配置GIT

使用以下命令设置用户名，将“dailaoda45”中的内容替换为您的名字。

```
git config --global user.name “dailaoda45”
```

**第 2 步：**

运行此命令设置电子邮件地址，将“[email ”中的内容替换为您的用户电子邮件。

```
git config --global user.email daichangyi940713@foxmail.com 
```

### 第 3 步：检查 GIT 设置

下面的命令列出了对 Git 配置文件所做的更改，如屏幕截图所示。

```sql
git config --list
```

### 第 4 步（可选）：GIT 配置



如果您想编辑设置，可以随时使用以下命令更改它们：

git 配置

查看常用git命令可运行下面命令查看 

```
git config
```


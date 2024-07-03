---
title: 换电脑后linux下迁移恢复HEXO
author: 戴昌益
date: 2024-7-3 9:52:07
tags: [博客部署安装]
categories: 技
---

# 换电脑后linux下迁移恢复HEXO



1、安装好git后拉取或者上传备份好的source文件。我这里有备份在github.io上的source分支中。

```
git clone https://github.com/dailaoda45/dailaoda45.github.io.git
```

2、安装node.js

1、下载node.js

这里使用wget直接下载到服务器也可以网站上下载下来后自行上传到服务器。

2、/usr/local下创建目录

```
cd /usr/local
mkdir nodejs
```

3、移动到nodejs中

```
cd /usr/local/nodejs
```

4、下载node.js包

```
# 安装npm
apt install npm
# 这里不知道为什么就自带了nodejs
```

5、查看版本

```
npm -v
nodejs -v
```

6、安装 Hexo

所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。

```
$ npm install -g hexo-cli
```

此时显示

```
npm install -g hexo-cli

   required: { node: '>=14' },
npm WARN EBADENGINE   current: { node: 'v12.22.9', npm: '8.5.1' }
npm WARN EBADENGINE }
```



应该是需要升级node版本

运行

```
# 清除缓存
npm cache clean -f
# 下载node安装包
npm install -g n
# 升级到nodejs最新版本
n stable
# 查看当前版本
node -v
```

再次安装hexo提示下面内容。

```
changed 53 packages in 5s

14 packages are looking for funding
  run `npm fund` for details
```

不管继续往后执行


# 新方法

前面的安装好后发现不能用另外找了个方法

1、按前面的方法安装好git跟nodejs，还有npm

2、在备份文件夹中运行

```
# 安装hexo
npm install hexo-cli -g
#安装依赖（把之前删除的node_nodules文件装回来）
npm install 
# 下载hexo的git工具
npm install hexo-deployer-git --save

```

然后就可以正常的更新博客了

```
hexo clean 
hexo d

```


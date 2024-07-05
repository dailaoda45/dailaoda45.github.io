---
title: 记录删除通过yml文件生成的docker容器
author: 尘归尘|土归土
date: 2024-07-05 15:52:07
tags: [学习]
categories: 文|技

---

# 记录删除通过yml文件生成的docker容器

移除通过`docker compose -f /root/rustdesk-server.yml up -d`命令部署的容器

在`rustdesk-server.yml`配置了信息，后来发现胡乱抄了别人的信息发现不能用。要修改后重新弄。所以想删除刚刚上面生成的容器。

先使用

```
docker stop id
```

来停止对应的容器发现不行报错

```
+] Running 1/1
 ✘ Container hbbs  Error while Stopping 14.0s 
Error response from daemon: cannot stop container: 854372fa8df7a09bf8b348e54f98fc130d2c1e457c7a27d52a0f0a395b767fc3: permission denied
```

**试了一些方式发现解决不了不行**，

使用

```
aa-remove-unknown
```

然后来停止容易发现`docker`命令都没有了。

于是重启服务器

再来停止容器，奇迹般的成功了。

然后使用

```
docker compose down
```

删除容器发现不行，这个命令是用来删除 `docker-compose.yml`文件配置运行的容器。于是依葫芦画瓢

```
docker compose -f /root/rustdesk-server.yml down -d
```

就成功了。

下面命令可以删除所有已停止的容器。

```bash
docker compose rm -f
```
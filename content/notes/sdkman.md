+++
title = "sdkman"
author = ["liangGTY"]
draft = false
+++

java 版本管理安装


## command {#command}

```shell
sdk list java # 列出当前可安装的所有jdk版本
```

```shell
sdk install java x.y.z-open # x.y.z jdk具体版本号  不带后面子版本默认安装最新版本
```

```shell
sdk env init # 在当前目录创建环境文件
```

```shell
sdk use java 11.0.20-zulu # 当前目录使用指定jdk版本
```

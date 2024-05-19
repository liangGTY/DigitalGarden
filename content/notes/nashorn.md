+++
title = "nashorn"
author = ["liangGTY"]
draft = false
+++

jvm 上的js引擎


## 支持ES6 {#支持es6}

jdk默认是关闭了对es6的支持的，想要开启对es6的支持，需要设置一下jvm参数：

```shell
-Dnashorn.args=--language=es6
```

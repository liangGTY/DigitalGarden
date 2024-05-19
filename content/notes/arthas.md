+++
title = "arthas"
author = ["liangGTY"]
draft = false
+++

## cpu火焰图 {#cpu火焰图}

```shell
profiler start --event context-switches --duration 300 --file test.jfr
```


## 问题 {#问题}

```shell
thread -b # 会导致整个应用qps跌0
```

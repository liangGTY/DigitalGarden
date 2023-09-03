+++
title = "conductor"
author = ["liangGTY"]
draft = false
+++

netflix 开源的分布式[微服务编排]({{< relref "微服务编排.md" >}})引擎


## 为什么需要conductor {#为什么需要conductor}

参考 [why conductor](https://conductor.netflix.com/devguide/concepts/why.html). 其中的为什么不使用点对点编排 可以参考 [Peer-to-peer choreography and orchestration](https://xavyr-rademaker.medium.com/peer-to-peer-choreography-and-orchestration-544af8b1bcfb) 里面详细分析了点对点编排与微服务编排之间的区别和优劣


## 特点 {#特点}


### 可观察性 {#可观察性}

-   了解、调试和迭代任务和工作流程执行。
-   对工作流程进行细粒度操作控制，能够暂停、恢复、重新启动、重试和终止


### 底层各存储可插拔 {#底层各存储可插拔}

-   持久化
-   任务队列
-   index


## 组件 {#组件}

-   [orkes-queues](https://github.com/orkes-io/orkes-queues) orkes的队列实现
-   [conductor-community](https://github.com/Netflix/conductor-community) conductor社区 提供相关模块的支持

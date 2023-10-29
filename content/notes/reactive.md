+++
title = "Reactive"
author = ["liangGTY"]
draft = false
+++

最开始接触到 Reactive 是在刚毕业时开始使用RxJava进行编程的时候. 那时候分不清一些概念. 经常混淆, 误以为是一回事.


## Reactive {#reactive}

反应式 和 DDD(领域驱动设计) 一样, 并不指代某些具体的技术. 而是一种理念、架构设计原则([The Reactive Principles](https://www.reactiveprinciples.org/principles/index.html)). 当然 反应式和DDD 也并不是对立的.

通常我们在软件设计背景下讨论 “Reactive” 一般指代以下两个概念

1.  反应式编程(编程范式)
2.  反应式系统(架构和设计)


## Reactive System {#reactive-system}

反应式系统是一种架构风格, 通常允许多个单体应用程序组成服务, 对一系列的请求进行响应, 通常反应式系统具备以下几个特质

1.  即时响应性
2.  回弹性
3.  弹性
4.  消息驱动

这几个特质描述都比较抽象, 具体描述可以查看 [反应式宣言](https://www.reactivemanifesto.org/zh-CN)


## Reactive programming {#reactive-programming}

> 反应式编程 (reactive programming) 是一种基于数据流 (data stream) 和 变化传递 (propagation of change) 的声明式 (declarative) 的编程范式。

反应式编程是用于构建响应式系统的重要技术之一, 但并不是唯一选择, 通常建议将反应式编程技术与反应式系统的设计原则相结合.


## Reactive Extensions {#reactive-extensions}

反应式编程原则的具体实现, 包括但不限于 Rx\* / Project Reactor / Akka Stream / Vert.x /


## Reactive Streams {#reactive-streams}

Reactive Streams 是一项为具有非阻塞背压的异步流处理提供标准的举措。这包括针对运行时环境（JVM 和 JavaScript）以及网络协议的努力。

在反应式编程早期, 并没有一个统一的实现规范 所以每个 Reactive Extensions 都各自实现了一套自己的API规范, 且相互之间无法互操作, 为了解决这个问题 Reactive Streams 规范才被制定出来.

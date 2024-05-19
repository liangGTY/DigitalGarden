+++
title = "zuul"
author = ["liangGTY"]
draft = false
+++

## LoadBalancer 原理 {#loadbalancer-原理}

内部会维护一个 serverListImpl 以及 serverListUpdater， updeter会定时出发列表更新 有定时 有监听eureka事件的

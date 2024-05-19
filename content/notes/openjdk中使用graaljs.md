+++
title = "openjdk中使用graaljs"
author = ["liangGTY"]
draft = false
+++

jdk17中废弃了nashorn引擎， 如果需要在jdk中使用js引擎 需要使用额外的js引擎 比如graaljs。 如果是在graalvm中使用 无需进行额外配置， 如果在非grallvm的jdk中使用 需要额外配置

可以参考 [graaljs-in-jdk-demo](https://github.com/graalvm/graal-js-jdk11-maven-demo/blob/master/README.md)

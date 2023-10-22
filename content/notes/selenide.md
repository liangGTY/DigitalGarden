+++
title = "Selenide"
author = ["liangGTY"]
draft = false
+++

构建在 Selenium 之上的api层


## Proxy {#proxy}

```gradle
    testImplementation('com.codeborne:selenide:6.18.0')
    testImplementation ('com.codeborne:selenide-proxy:6.18.0')
```

```java
        Configuration.proxyEnabled = true;
        open();
        com.browserup.bup.BrowserUpProxy proxy = WebDriverRunner.getSelenideProxy().getProxy();
        proxy.setHarCaptureTypes(CaptureType.getAllContentCaptureTypes());
        proxy.enableHarCaptureTypes(CaptureType.REQUEST_CONTENT, CaptureType.RESPONSE_CONTENT);
        proxy.newHar("pofig");
        open("https://baidu.com");

        String text = collect.get(0).getResponse().getContent().getText();

        System.out.println(text);
```

注意 如果页面有异步请求的化 很有可能抓取不到数据 可以在中间 sleep 一下

+++
title = "My-Mac"
author = ["liangGTY"]
draft = false
+++

[my-ios]({{< relref "my_ios.md" >}})


## MacOS {#macos}

{{< figure src="/assets/my-mac.png" >}}


## Applications {#applications}


### Productivity {#productivity}

-   [alfred]({{< relref "alfred.md" >}}) 启动器
-   [Contexts](https://contexts.co) 窗口切换器
-   [yabai]({{< relref "yabai.md" >}}) 平铺式窗口管理
-   [karabiner]({{< relref "karabiner.md" >}}) 键盘自定义软件
-   [surge]({{< relref "surge.md" >}}) 网络调试软件 &amp; 通往新世界的桥梁
-   [CleanShot](https://cleanshot.com) 截屏软件
-   [NetNewWire](https://netnewswire.com/) RSS订阅
-   [1Password](https://1password.com/) 跨平台密码管理器
-   [Fantastical](https://flexibits.com/fantastical) 日历
-   [AppCleaner](https://freemacsoft.net/appcleaner/) mac软件卸载工具. 可让你彻底卸载不需要的应用程序
-   ~~Obsiaian 双链笔记软件~~ 已切换至 [org-roam]({{< relref "org_roam.md" >}}) v2
-   [BetterDisplay](https://github.com/waydabber/BetterDisplay) 强大的外置显示器控制


### Code {#code}

-   [Idea]({{< relref "idea.md" >}}) Java工程师的首选
-   [emacs]({{< relref "emacs.md" >}}) 神的编辑器
-   [Vim]({{< relref "vim.md" >}}) 编辑器之神
-   [vs-code]({{< relref "vs_code.md" >}}) 主要用于看一些JS项目
-   [warp](https://www.warp.dev/) 我的主要终端
-   [Sublime Merge]({{< relref "sublime_merge.md" >}}) Git client. 超喜欢它的深度[定制化](https://www.sublimemerge.com/docs/)能力. 通常也会搭配 [magit]({{< relref "magit.md" >}}) 一起使用
-   [Paw](https://paw.cloud) HTTP client


### CommandLine {#commandline}

-   [neofetch](https://github.com/dylanaraps/neofetch) 在命令行显示操作系统信息、软件和硬件信息
-   [ripgrep](https://github.com/BurntSushi/ripgrep) rust版的grep 主打就是一个快
-   [rga](https://github.com/phiresky/ripgrep-all) 类似 ripgrep 但是可以搜索PDF zip里的内容
-   [sdkman]({{< relref "sdkman.md" >}}) java sdk版本管理


## [macos-defaults](https://macos-defaults.com/) {#macos-defaults}


### key repeat rate # 按键重复速率 {#key-repeat-rate-按键重复速率}

```shell
defaults write -g InitialKeyRepeat -int 10 # normal minimum is 15 (225 ms)
defaults write -g KeyRepeat -int 1 # normal minimum is 2 (30 ms)
```


### Mac Rearrange automatically {#mac-rearrange-automatically}

```shell
sudo defaults write com.apple.dock "mru-spaces" -bool "false" && killall Dock
```

system setting --&gt; Desktop &amp; Dock --&gt; Automatically rearrange Spaces based on most recent use


### Key held down behavior {#key-held-down-behavior}

```shell
defaults write NSGlobalDomain "ApplePressAndHoldEnabled" -bool "false"
```

+++
title = "ivy"
author = ["liangGTY"]
draft = false
+++

## install {#install}


### doom emacs {#doom-emacs}

init.el 中添加如下代码

```elisp
(ivy +childframe +fuzzy +icons +prescient)
```


#### childframe {#childframe}

开启 ivy-posframe 扩展


## function {#function}


### ivy-immediate-done {#ivy-immediate-done}

默认绑定在 C-M-j. 作用是直接使用用户输入的内容回车 而不是当前minibuffer里的候选项 9


## Expand {#expand}

-   [ivy-posframe](https://github.com/tumashu/ivy-posframe) 可以在其他地方显示候选列表
-   [ivy-prescient](https://github.com/tumashu/ivy-posframe) 智能的过滤和排序候选列表


## Link {#link}

-   [ivy 新手教程](https://emacs-china.org/t/ivy/12091)

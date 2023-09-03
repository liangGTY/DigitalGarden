+++
title = "emacs debug"
author = ["liangGTY"]
tags = ["emacs"]
draft = false
+++

## 如何debug? {#如何debug}

1.  在需要debug的函数上(光标置于此函数上) 执行 (edebug-defun) 函数. 添加断点
2.  edebug-remove-instrumentation 用于删除断点
3.  快捷键
    1.  n 下一步
    2.  q 退出debug


## 常见问题 {#常见问题}


### edebug-defun 不生效 {#edebug-defun-不生效}

执行函数后 需要按下 d 才会进入debug模式 不知道为什么?

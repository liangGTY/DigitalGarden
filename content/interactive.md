+++
title = "interactive"
author = ["liangGTY"]
draft = false
+++

emacs function 如果想交互式调用 (M-x) 访问 则必须加上 (interactive)

```elisp
(defun my_function ()
  (interactive)
  (message "This is a great function")))
```


## Link {#link}

-   <https://emacs.stackexchange.com/questions/3555/what-is-the-difference-between-a-function-and-a-command>

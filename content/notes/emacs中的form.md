+++
title = "emacs中的form"
author = ["liangGTY"]
tags = ["emacs"]
draft = false
+++

在 Lisp 中，我们称 words 为 atoms ， atom 的意思是不可分割的。对 Lisp 而言, words 是用在 list 中的，并且是不可以被再分割为其他再小部分的仍然是作为程序的一部分的。

在一个 list 中， atoms 之间是通过空格来分隔的。

从技术上讲，一个 list 是由括号包围着由空格分隔的 atoms 或由其他的 list 或 atoms 和其他 list 一起组成的。一个 list 可以仅有一个 atom 或什么都没有。一个什么也没有的 list 看起来像这样子： () ，它称为空 list. 不同于其他，一个空 list 是可以同时看作是一个 atom 和 一个 list 的。

以人类可读的文本形式表达半结构化数据的(原文为 The printed representation of ，我采用维基百科的定义来意译) 1 atom 和 list 都被称为 symbolic expressions 或更简洁地称为 S-expressions . 单词 expression 它自身可以指人类可读的文本形式，或者指 atom 又或者是 list . 通常是使用 expression 来统称它们（在文本上，\*form\* 是 expression 的同义词）

[GNU Emacs Lisp 学习笔记](https://emacsist.github.io/emacsist/elisp/GNU%20emacs%20lisp%E5%AD%A6%E4%B9%A0%E7%AC%94%E8%AE%B0.html#org11dfcbc)

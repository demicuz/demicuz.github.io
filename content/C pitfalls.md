---
title: "C pitfalls"
date: "2022-11-19"
---

Using `f()` instead of `f(void)` in [[C++]] they're equivalent, but not in C. In C `f()` is a function with *unspecified* arguments. See [this](https://nrk.neocities.org/articles/c-stop-writing-old-function-decel.html).

Using `strlcpy` is inefficient, see [[Strings in C]].
---
title: "std::vector"
date: "2023-03-07"
aliases: ["std::vector"]
---

**Doesn't** check if index is valid or not when using `data[i]`. Use `.at(i)` to throw an exception if index is invalid.

`.front()` and `.back()` on an empty vector is UB. I'm not sure how I feel about this. Use `.empty()` to check for emptiness.

Some useful methods:
- `.push_back()`, `.pop_back()`
- `.empty()`, `.size()`, `.capacity()`
- `.reserve()`, `.resize()`
- `.back()`
- `.clear()` (capacity stays the same)
- `.begin()`, `.end()`, `.rbegin()`, `.rend()`

### Links
- [Векторы и строки - Основы С++](https://academy.yandex.ru/handbook/cpp/article/vectors-and-strings)

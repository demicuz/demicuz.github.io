---
title: "Tail recursion"
date: "2022-09-05"
---

A kind of recursion when a function returns a call to itself with different arguments. No computation happens after that.

Allows for tail call optimization, which avoids allocating a new stack frame for each recursive call. It substitutes recursion with a for-loop essentially.

### Links
- [What is tail recursion?](https://stackoverflow.com/questions/33923/)
- [What is tail call optimization?](https://stackoverflow.com/questions/310974/)
---
title: "C (language)"
aliases: [C]
tags: [coding/language]
---

### Resources
- [oz123/awesome-c](https://github.com/oz123/awesome-c)

### Useful stuff
- [[C tricks]]
- [[Dynamic memory allocation in C]]
- [[Pointers in C]]
- [[Makefile]]
- [[C compilation and debugging]]
- [[Building C]]
- [[C linting and formatting]]
- [[Static variables]]
- [[File IO in C]]
- [[Error handling in C]]

### Useful tools
- [[GDB|GDB]]
- [[LLDB]]
- [rr: lightweight recording & deterministic debugging](https://rr-project.org/)

### Random notes
`NULL` pointer in GNU compiler (gcc) is guaranteed to be equal to `0` (see [this page](https://www.gnu.org/software/libc/manual/html_node/Null-Pointer-Constant.html)). Also `NULL` can be put into `free()`. `malloc(0)` may return a unique pointer or `NULL`.

### #todo 
- You can initialize only first `n` elements of an array. Like only the first:
```C
char buffer[100] = {0};
```
- `extern` keyword
- `static` and `inline` functions

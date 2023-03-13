---
title: "C (language)"
aliases: [C]
tags: [coding/language]
date: "2022-08-15"
lastmod: "2022-08-15"
---

### Resources
- [[Awesome C and C++]]
- [oz123/awesome-c](https://github.com/oz123/awesome-c)

### Useful stuff
#todo too many!
- [[C tricks]]
- [[Dynamic memory allocation in C]]
- [[Memory management in C]]
- [[C declarations]]
- [[Pointers in C]]
- [[struct in C]]
- [[Strings in C]]
- [[`typedef` in C]]
- [[C macros]]
- [[Advanced C syntax]]
- [[Makefile]]
- [[C debugging, compilation and building]]
- [[Making libraries]]
- [[C linting and formatting]]
- [[Static variables]]
- [[File IO in C]]
- [[Error handling in C]]
- [[C and C++ lingo]]

### Useful tools
- [[GDB|GDB]]
- [[LLDB]]
- [rr: lightweight recording & deterministic debugging](https://rr-project.org/)

### Random notes
`NULL` pointer in GNU compiler (gcc) is guaranteed to be equal to `0` (see [this page](https://www.gnu.org/software/libc/manual/html_node/Null-Pointer-Constant.html)). Also `NULL` can be put into `free()`. `malloc(0)` may return a unique pointer or `NULL`.

You can include `stddef.h` instead of `stdlib.h` for `NULL` and `size_t`.

You can declare an `enum` inside of a `struct`. It will act the same as if it was defined in the outer scope.

### #todo 
- `static` and `inline` functions (see [this](https://stackoverflow.com/questions/31108159/))
- automatic header generation, maybe with `makeheaders`
- how does the assembly look when one struct is returned from a function and assigned to another struct?

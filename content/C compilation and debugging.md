---
title: "C compilation and debugging"
date: "2022-10-27"
lastmod: "2022-10-27"
---

- [[GDB]]

### Headers
If you use `#include "my_header.h"` syntax (with `""` instead of `<>`) and your header lies in the directory with `.c` files, then no need to tell the compiler to search for headers. E.g. `gcc <your_c_files>` will be enough. If you have a whole bunch of headers in some directory, you can tell the compiler to search in that directory by using `gcc <your_c_files> -I <header_directory>`. Something like `./include/` would do.

In short, `""` means relative path, `<>` means libraries from C and pointed with `-I`. See [c - What are the benefits of a relative path such as "../include/header.h" for a header?](https://stackoverflow.com/questions/597318/).

### Useful info
- [An Introduction to GCC](https://www.linuxtopia.org/online_books/an_introduction_to_gcc/)
- [CPP/C++ Compiler Flags and Options](https://caiorss.github.io/C-Cpp-Notes/compiler-flags-options.html)
	- [GCC optimization flags](https://gcc.gnu.org/onlinedocs/gcc/Optimize-Options.html)
- [A Whirlwind Tutorial on Creating Really Teensy ELF Executables for Linux](https://www.muppetlabs.com/~breadbox/software/tiny/teensy.html) (creating a small binary)

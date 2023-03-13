---
title: "C debugging, compilation and building"
date: "2022-10-27"
lastmod: "2022-10-27"
---

### Related
- [[GDB]]
- [[C and C++ building tools]]
- [[Making libraries]]
- [[C linking]]
- [[C and C++ compiler flags and options]]

### Headers
`#include` with `""` means relative path or directories added with `-I`, with `<>` means system headers or directories added with `-I`. It's a bit more complicated actually, but I don't care. See [c - What are the benefits of a relative path such as `"../include/header.h"` for a header?](https://stackoverflow.com/questions/597318/) and [How to use `#include` directive correctly?](https://stackoverflow.com/questions/464560/)

### Libraries

There are static and dynamic [[Library (computing)|libraries]].

How to create static and shared libraries: [C Programming Tutorial: Creating Libraries](https://randu.org/tutorials/c/libraries.php).

Static libraries can be built with an ancient `ar` technology: `ar rcs <libname.a> <...object files>`. Also you should declare all functions that you don't want to leak to the outside world as `static`. See also [[Making libraries]].

See [this](https://stackoverflow.com/questions/63444418/gcc-how-to-create-an-so-from-a-source-file-and-other-o-files) in case you want to build a shared library. 

See also [How do you actually use a C library? - Stack Overflow](https://stackoverflow.com/questions/1749079/how-do-you-actually-use-a-c-library).
**Important note** - you can actually redefine functions from a library. Functions from libraries are used only when they're not found in your code. See [this](https://stackoverflow.com/questions/24390267/why-redefinition-of-a-function-which-is-already-present-in-dynamic-or-static-lib).

If a function is contained in two static libraries and you use both of them, then the implementation which comes in the **first** included library will be used. Weird.
UPD: I think it's important how your object files are named. If the function is contained in both libraries, but the object files are named different, there **will** be a multiple declaration error.

### pkg-config
Used for getting all the right dependencies. Usage on [[Cairo]] hello world:
```shell
cc hello.c -o hello $(pkg-config --cflags --libs cairo)
```

Libraries should be added as linker flags, AFTER stating what files you are compiling. [See here](https://stackoverflow.com/a/34479058).

### Useful info
- [An Introduction to GCC](https://www.linuxtopia.org/online_books/an_introduction_to_gcc/)
- [CPP/C++ Compiler Flags and Options](https://caiorss.github.io/C-Cpp-Notes/compiler-flags-options.html)
	- [GCC optimization flags](https://gcc.gnu.org/onlinedocs/gcc/Optimize-Options.html)
- [A Whirlwind Tutorial on Creating Really Teensy ELF Executables for Linux](https://www.muppetlabs.com/~breadbox/software/tiny/teensy.html) (creating a small binary)

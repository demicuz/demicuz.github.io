---
title: "Building C"
date: "2022-11-16"
lastmod: "2022-11-16"
---

### Libraries

There are static and dynamic [[Library (computing)|libraries]].

How to create static and shared libraries: [C Programming Tutorial: Creating Libraries](https://randu.org/tutorials/c/libraries.php).

Static libraries can be built with an ancient `ar` technology: `ar rcs <libname.a> <...object files>`. Also you should declare all functions that you don't want to leak to the outside world as `static`.

See [this](https://stackoverflow.com/questions/63444418/gcc-how-to-create-an-so-from-a-source-file-and-other-o-files) in case you want to build a shared library. 

See also [How do you actually use a C library? - Stack Overflow](https://stackoverflow.com/questions/1749079/how-do-you-actually-use-a-c-library).
**Important note** - you can actually redefine functions from a library. Functions from libraries are used only when they're not found in your code. See [this](https://stackoverflow.com/questions/24390267/why-redefinition-of-a-function-which-is-already-present-in-dynamic-or-static-lib).

If a function is contained in two static libraries and you use both of them, then the implementation which comes in the **first** included library will be used. Weird.
UPD: I think it's important how your object files are named. If the function is contained in both libraries, but the object files are named different, there **will** be a multiple declaration error.

### Other thingies
- [[C compilation and debugging]]
- [[Meson build system]]
- [[Making libraries]]
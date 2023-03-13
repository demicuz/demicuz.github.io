---
title: "File I/O in C"
date: "2023-01-25"
lastmod: "2023-01-25"
---

`#include <fcntl.h>`, `open()` and there you go. Don't forget to `close()`.

There are also `fread()` and friends.

And `mmap`. I haven't touched it yet, but the idea seems pretty cool - map the file to virtual address space and have fun with it.
---
title: "struct in C"
date: "2022-08-23"
---

### Padding
tbd. The order of fields matters. Keep the smallest fields at the end for better alignment. The compiler **won't** do this for you (because it violates [the standard](https://stackoverflow.com/a/118177)).

- [The Lost Art of Structure Packing](http://www.catb.org/esr/structure-packing/)

### Flexible members
 Members of struct whose size is not known at compile time. See [the rules](https://stackoverflow.com/a/26818050).

### Links
- [Why can't C compilers rearrange struct members to eliminate alignment padding?](https://stackoverflow.com/questions/9486364/)
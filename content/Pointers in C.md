---
title: "Pointers in C"
date: "2022-08-23"
lastmod: "2022-08-23"
---

### Pointer size
The size of a pointer is dependent on the machine for which the code is compiled. On 64-bit computers it's 64 bits. It also can be different from `size_t` size, which can hold the size of the largest object.

**It's not guaranteed** by the standard that all pointers are the same size. But on practice they are. It's guaranteed that `char *` and `void *` are the same size, all `struct *` the same size, all `union *`, etc.

Casting pointers to `unsigned long` to do various things with them can cause **undefined behavior**! Whether `unsigned long` is the same size as a pointer is machine-dependent. Use `uintptr_t` instead. ^96aaca

**References**:
- [What is the size of a pointer in C? - Quora](https://www.quora.com/What-is-the-size-of-a-pointer-in-C)
- [Are all data pointers the same size in one platform for all data types?](https://stackoverflow.com/questions/1241205/)
- [Printing the Value of a Pointer to an Object](https://riptutorial.com/c/example/12982/printing-the-value-of-a-pointer-to-an-object)
- [c++ - What is uintptr_t data type - Stack Overflow](https://stackoverflow.com/questions/1845482/what-is-uintptr-t-data-type)

### Links
- [How many instructions to access pointer in C?](https://stackoverflow.com/questions/2747517)
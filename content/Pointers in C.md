---
title: "Pointers in C"
---

### Pointer size
The size of a pointer is dependent on the machine for which the code is compiled. On 64-bit computers it's 64 bits. It also can be different from `size_t` size, which can hold the size of the largest object.

Casting pointers to `unsigned long` to do various things with them can cause <mark style="background: #FF5582A6;">undefined behavior</mark>! Whether `unsigned long` is the same size as a pointer is machine-dependent. Use `uintptr_t` instead. ^96aaca

**References**:
- [What is the size of a pointer in C? - Quora](https://www.quora.com/What-is-the-size-of-a-pointer-in-C)
- [Printing the Value of a Pointer to an Object](https://riptutorial.com/c/example/12982/printing-the-value-of-a-pointer-to-an-object)
- [c++ - What is uintptr_t data type - Stack Overflow](https://stackoverflow.com/questions/1845482/what-is-uintptr-t-data-type)

### Links
- [How many instructions to access pointer in C?](https://stackoverflow.com/questions/2747517)

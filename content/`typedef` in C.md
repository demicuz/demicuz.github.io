---
title: "`typedef` in C"
date: "2023-01-04"
---

Define your own types!
```C
typedef struct {
	char *name;
	int age;
} Person;

Person p = {.name = "John", .age = 42};
```

### Arrays
From [Wikipedia](https://en.wikipedia.org/wiki/Typedef#Arrays):

> ```C
> typedef char arrType[6];
> 
> arrType arr = {1, 2, 3, 4, 5, 6};
> arrType *pArr; // a pointer to an array -> a pointer to a pointer to a char
> 
> // Same as:
> // char arr[6] = {1, 2, 3, 4, 5, 6};
> // char (*pArr)[6];
> ```
> Here, `arrType` is the new alias for the `char[6]` type, which is an array type with 6 elements. For `arrType *pArr;`, `pArr` is a pointer pointing to the memory of the `char[6]` type.

It's not obvious **at all**. This would be far more logical:
```C
typedef char[6] arrType;
```

Why is it not that way? [Fuck you](https://cseweb.ucsd.edu/~ricko/rt_lt.rule.html), that's why.
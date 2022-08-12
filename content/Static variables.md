---
title: "Static variables"
---

Check out this [[C (language)|C]] code:
```C
#include <stdio.h>

void foo()
{
	static int a = 5;
	printf("foo: %d\n", a++);
}

void bar()
{
	static int a = 42;
	printf("bar: %d\n", a++);
}

int main(void)
{
	foo();
	bar();
	foo();
	bar();
	foo();
	bar();
	return 0;
}
```
Output:
```
foo: 5
bar: 42
foo: 6
bar: 43
foo: 7
bar: 44
```
Cool, huh?

### Notes
Local `static` variables have some benefits over `global` variables. You can have multiple `static` variables that are named the same, but used in different functions. And they're isolated from other functions. Cool!

It's impossible to have a static variable inside a struct. That defeats their whole purpose, as their variables are stored together, like in array. But it's possible to have a `static` struct!

A possible downside - the memory for static objects is allocated in the data segment. That means they're not freed until the termination of a program.

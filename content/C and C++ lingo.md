---
title: "C and C++ lingo"
date: "2022-08-17"
---

### declaration vs definition
Declaration - you're telling the compiler "there's something with this name, and it has this type". Example:
```C
int hello();
```

Definition - providing all the details. For functions it means providing function body. Example:
```C
int hello()
{
  return 420;
}
```

For more info see:
[What's the difference between declaring and defining in C and C++](https://www.cprogramming.com/declare_vs_define.html)

### Translation unit
Take a `.c` file, put in a preprocessor - you get a translation unit that is turned into an `.o` file after compilation. See also [on Wikipedia](https://en.wikipedia.org/wiki/Translation_unit_(programming)).
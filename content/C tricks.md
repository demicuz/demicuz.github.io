---
title: "C tricks"
date: "2023-01-06"
lastmod: "2023-01-06"
---

[[C (language)]]

You can do arithmetic with `char`s. So to convert number `n` to char you can do
```C
'0' + n
```

You can also do that with the results of logical operations (if you want to annoy somebody):
```C
123 + (n > 0)
```

You can [detect](https://www.geeksforgeeks.org/how-to-detect-operating-system-through-a-c-program/) an operating system on which the code is executed:
```C
#ifdef __linux__
// Some linux-specific code
#endif
#ifdef __APPLE__
// Some Apple-specific code
#endif
```

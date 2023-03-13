---
title: "Python quirks"
date: "2022-12-20"
---

### Modulo
Modulo and integer division works [differently](https://stackoverflow.com/questions/3883004) from C! In C it's:
```
7 % 3 = 1
-7 % 3 = -1
7 % -3 = 1
-7 % -3 = -1
```

But in Python:
```
>>> 7 % 3
1
>>> -7 % 3
2
>>> 7 % -3
-2
>>> -7 % -3
-1
```

Aaand for Python's `Decimal` it's different. So yeah, more ways to [[Shooting yourself in the foot|shoot yourself in the foot]].

### Tuples
This is not a tuple:
```Python
a = (123) # int
```

This is a tuple:
```python
b = (123,) # tuple
```

### Call stack limit
By default, call stack is limited to 1000 frames. Weird, but OK.

### Links
- [Common Gotchas — The Hitchhiker's Guide to Python](https://docs.python-guide.org/writing/gotchas/)
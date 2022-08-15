---
title: "Python"
aliases: [Петухон]
tags: [coding/language]
---

### Notes
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

### #todo 
- [Combinations - Rosetta Code](https://rosettacode.org/wiki/Combinations#Python) (Python example). Really worth attention. Didn't know `[i + 1:]` syntax is valid

### Links
- [Learn Python - Free Interactive Python Tutorial](https://learnpython.org/)

### See also
- [[Awesome Python]]
- [[Python package management]]

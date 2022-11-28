---
title: "Strings in C"
date: "2022-11-19"
---

Just a null-terminated array of characters. That sucks, as it's extremely easy to [[Shooting yourself in the foot|shoot yourself in the foot]]. `strlcpy` and friends won't save you. In general, you have to know the length of your string before doing anything with it.

### Links
- [I'm not a fan of strlcpy(3)](https://nrk.neocities.org/articles/not-a-fan-of-strlcpy.html)
- [strcpy: a niche function you don't need](https://nullprogram.com/blog/2021/07/30/) by [[null program (blog)]]
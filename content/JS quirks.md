---
title: "JS quirks"
---

### All numbers are floating-point
So `9007199254740992 + 1` is `9007199254740992`. You probably should use `BigInt` for this.
- [How numbers are encoded in JavaScript](https://2ality.com/2012/04/number-encoding.html)

### `null` is an object. Kind of.
`typeof` returns `"object"` for the `null` type. This is a known issue in JavaScript since its first release.

### Division by zero is not UB
It's either `Infinity` or `-Infinity`. Also there's `0` and `-0`. So `1/0` is `Infinity` and `1/-0` is `-Infinity`. Division by zero is only undefined for `±0/±0` and `±∞/±∞`.
- [javascript - Are +0 and -0 the same?](https://stackoverflow.com/questions/7223359)

### `self` vs `window`
`self` is a more portable way of using a global object. In browser `self` defaults to `window`.
- [Difference between this and self in JavaScript](https://stackoverflow.com/questions/16875767)

---
title: "JS syntax"
date: "2022-11-13"
lastmod: "2022-11-13"
---

#tbd 
Spread operator `...`, `forEach`

`for ... of` - like `for elem in stuff` in Python:
```js
const iterable = [10, 20, 30];

for (let value of iterable) {
  value += 1;
  console.log(value);
}
// 11
// 21
// 31
```

To enumerate an array with its indices:
```js
for (const [i, v] of arr.entries()) {
  console.log(i, v); // Prints "0 a", "1 b", "2 c"
}
```

**`for...in`** iterates over all [enumerable string properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties) of an object (ignoring properties keyed by [symbols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)), including inherited enumerable properties:
```js
const object = { a: 1, b: 2, c: 3 };

for (const property in object) {
  console.log(`${property}: ${object[property]}`);
}

// "a: 1"
// "b: 2"
// "c: 3"
```

`Array.prototype.forEach()` - like `for ... of`, but with caveats, I don't remember what exactly.

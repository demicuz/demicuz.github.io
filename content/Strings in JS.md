---
title: "Strings in JS"
---

They're either UTF-16 or UCS-2 (now obselete). Depends on the interpreter. Each character takes up 1 or 2 bytes. UTF-16 is the only UTF that is not compatible with ASCII.

To decode a string from a typed array use:
```js
new TextDecoder("utf-8").decode(uint8array); // or utf-16
```

### To learn
Can I safely use `someString[i]` syntax? Some characters can take up 1 byte, and some 2. There's `String.prototype.codePointAt()`, I think it solves this problem.

### Links
- [How many bytes in a JavaScript string?](https://stackoverflow.com/questions/2219526)
- [How to convert an Uint8Array to string in Javascript](https://ourcodeworld.com/articles/read/164/how-to-convert-an-uint8array-to-string-in-javascript)

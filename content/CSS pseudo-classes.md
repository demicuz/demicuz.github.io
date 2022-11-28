---
title: "Pseudo-classes"
date: "2022-11-15"
---

### `:has()`
```CSS
/* Selects an h1 heading with a
paragraph element that immediately follows
the h1 and applies the style to h1 */
h1:has(+ p) { margin-bottom: 0; }
```
---
title: "CSS basics"
date: "2022-11-15"
lastmod: "2022-11-15"
---

### Selectors
Type selectors, e.g. `h1` or `::before`. Avoid if possible.

`#` - id selectors ([doka](https://doka.guide/css/id-selector/))
```CSS
#first {
	color: red;
}
```

`.` - class selectors

See also [[CSS Complex selectors]].

### Inheritance
Some properties get inherited (mainly text style). I don't think it's a good idea to rely on that.

### Specificity
Specificity is a **weight** that is applied to a given CSS declaration, determined by the number of each [selector type](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity#selector_types) in the matching selector.

### Cascade
An algorithms that defines how to combine property values originating from different sources.

Just remember that using `!important` can be dangerous and that properties declared **later** (at the bottom) have higher priority.

### Flow
If elements are in flow, they adhere to rules of [[inline and block elements]]. See [In Flow and Out of Flow | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout/In_Flow_and_Out_of_Flow).

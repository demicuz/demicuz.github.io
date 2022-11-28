---
title: "Vue pitfalls"
date: "2022-11-21"
---

You should avoid using arrow functions when defining `methods`, as that prevents Vue from binding the appropriate `this` value:
```js
export default {
  methods: {
    increment: () => {
      // BAD: no `this` access here!
    }
  }
}
```

When using in-DOM templates (templates directly written in an HTML file), you should avoid naming keys with uppercase characters, as browsers will coerce attribute names into lowercase:
```html
<a :[someAttr]="value"> ... </a>
```
The above will be converted to `:[someattr]` in in-DOM templates. If your component has a `someAttr` property instead of `someattr`, your code won't work. Templates inside Single-File Components are **not** subject to this constraint. [Source](https://vuejs.org/guide/essentials/template-syntax.html#dynamic-argument-syntax-constraints)

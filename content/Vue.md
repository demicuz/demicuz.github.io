---
title: "Vue"
---

### Learning
`computed properties` docs has some food for thought.

### Notes
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
The above will be converted to `:[someattr]` in in-DOM templates. If your component has a `someAttr` property instead of `someattr`, your code won't work. [Source](https://vuejs.org/guide/essentials/template-syntax.html#directives)

### Prefix shorthands
`v-bind` - `:` (`:some-attribute="..."`)
`v-on` - `@` (`@click="..."`)

### Links
- [Which dist files to use?](https://github.com/vuejs/core/tree/main/packages/vue#which-dist-file-to-use)
- [petite-vue - 6kb subset of Vue](https://github.com/vuejs/petite-vue)
- [Tutorial | Vue.js](https://vuejs.org/tutorial/#step-1)

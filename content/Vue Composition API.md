---
title: "Vue Composition API"
date: "2022-11-20"
---

`ref()` for reactive primitives, `reactive()` for reactive objects (arrays/maps/etc.). `ref()` is some kind of a wrapper around `reactive()`.

When using `ref()`, get proxy's value with `.value`:
```js
import { ref } from 'vue'

// reactive state
const count = ref(0)

// functions that mutate state and trigger updates
function increment() {
  count.value++
}
```

If you use `reactive()`, you **can't** reassign. Also see [ref vs reactive in Vue 3?](https://stackoverflow.com/questions/61452458/ref-vs-reactive-in-vue-3)

### Links
- [A basic tutorial](https://thecodest.co/blog/stop-using-options-api-in-vue)
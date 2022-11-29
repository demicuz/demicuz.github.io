---
title: "Vue"
date: "2022-11-20"
lastmod: "2022-11-20"
---

Create a project: `pnpm create vue@3`

- [[Vue basics]]
- [[Vue directives (advanced)]]
- [[Vue Composition API]]
- [[Vue pitfalls]]
- [[State management in Vue]]

### Projects
- [[Kanban board with Vue]]

### Learning
`computed properties` docs has some food for thought.

### Notes
Template expressions (`{{ }}`) are sandboxed and only have access to a [restricted list of globals](https://github.com/vuejs/core/blob/main/packages/shared/src/globalsWhitelist.ts#L3). The list exposes commonly used built-in globals such as `Math` and `Date`.

Globals not explicitly included in the list, for example user-attached properties on `window`, will not be accessible in template expressions. You can, however, explicitly define additional globals for all Vue expressions by adding them to [`app.config.globalProperties`](https://vuejs.org/api/application.html#app-config-globalproperties).

### Prefix shorthands
`v-bind` - `:` (`:some-attribute="..."`)
`v-on` - `@` (`@click="..."`)

### Links
- [Which dist files to use?](https://github.com/vuejs/core/tree/main/packages/vue#which-dist-file-to-use)
- [petite-vue - 6kb subset of Vue](https://github.com/vuejs/petite-vue)
- [Tutorial | Vue.js](https://vuejs.org/tutorial/#step-1)
- [Quick Start | Vue.js](https://vuejs.org/guide/quick-start.html)
- [Guide | Vue.js](https://vuejs.org/guide/essentials/application.html)
- [Examples | Vue.js](https://vuejs.org/examples/#hello-world)
---
title: "Vue directives (advanced)"
date: "2022-11-21"
---

Modifiers are special postfixes denoted by a dot, which indicate that a directive should be bound in some special way. For example, the `.prevent` modifier tells the `v-on` directive to call `event.preventDefault()` on the triggered event:
```html
<form @submit.prevent="onSubmit">...</form>
```

![](https://i.imgur.com/Pk9Ey4L.png)

Dynamic arguments:
```html
<a v-bind:[attributeName]="url"> ... </a>

<!-- shorthand -->
<a :[attributeName]="url"> ... </a>

```
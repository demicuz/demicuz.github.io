---
date: "2022-11-20"
lastmod: "2022-11-20"
---

### Directives
`v-bind`, or `:`
```html
<div v-bind:id="dynamicId"></div>
<div :id="dynamicId"></div>
```

`v-on`, or `@`
```html
<button v-on:click="increment">{{ count }}</button>
<button @click="increment">{{ count }}</button>
```

You can also use inline handlers:
```html
<button @click="count++">Add 1</button>
<p>Count is: {{ count }}</p>
```

`v-model`
See  [Form Input Bindings](https://vuejs.org/guide/essentials/forms.html).

`v-if`, `v-else-if`, `v-else`
Conditional rendering!
```html
<script setup>
import { ref } from 'vue'

const awesome = ref(true)

function toggle() {
  awesome.value = !awesome.value
}
</script>

<template>
  <button @click="toggle">toggle</button>
  <h1 v-if="awesome">Vue is awesome!</h1>
  <h1 v-else>Oh no 😢</h1>
</template>
```

`v-for`
Rendering lists!
Always use `:key` binding (it's a special attribute for `v-for` stuff). The `key` allows Vue to accurately move each `<li>` to match the position of its corresponding object in the array.
```html
<ul>
  <li v-for="todo in todos" :key="todo.id">
    {{ todo.text }}
  </li>
</ul>
```

`ref`
Use this to manipulate the DOM from Vue! Example:
```html
<script setup>
import { ref, onMounted } from 'vue'

const p = ref(null)

onMounted(() => {
  p.value.textContent = 'mounted!'
})
</script>

<template>
  <p ref="p">hello</p>
</template>
```

### Lifecycle hooks
The most common are `onMounted()`, `onUpdated()` and `onUnmounted()`. See [the docs](https://vuejs.org/guide/essentials/lifecycle.html#registering-lifecycle-hooks).
```html
<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  console.log(`the component is now mounted.`)
})
</script>
```

### Watchers
If you need to perform a side-effect when some value changes, use watchers:
```html
<script setup>
import { ref, watch } from 'vue'

const todoId = ref(1)
const todoData = ref(null)

async function fetchData() {
  todoData.value = null
  const res = await fetch(
    `https://jsonplaceholder.typicode.com/todos/${todoId.value}`
  )
  todoData.value = await res.json()
}

fetchData()

watch(todoId, fetchData)
</script>

<template>
  <p>Todo id: {{ todoId }}</p>
  <button @click="todoId++">Fetch next todo</button>
  <p v-if="!todoData">Loading...</p>
  <pre v-else>{{ todoData }}</pre>
</template>
```

### Props
You can pass properties to child components!
```html
<script setup>
import { ref } from 'vue'
import ChildComp from './ChildComp.vue'

const greeting = ref('Hello from parent')
</script>

<template>
  <ChildComp :msg="greeting" />
</template>
```

`ChildComp.vue`:
```html
<script setup>
const props = defineProps({
  msg: String
})
</script>

<template>
  <h2>{{ msg || 'No props passed yet' }}</h2>
</template>
```

### Emits
Pass stuff **from child** to parent:
```html
<script setup>
import { ref } from 'vue'
import ChildComp from './ChildComp.vue'

const childMsg = ref('No child msg yet')
</script>

<template>
  <ChildComp @response="(msg) => childMsg = msg" />
  <p>{{ childMsg }}</p>
</template>
```

`ChildComp.vue`:
```html
<script setup>
const emit = defineEmits(['response'])

emit('response', 'hello from child')
</script>

<template>
  <h2>Child component</h2>
</template>
```

### Slots
Like [[#Props]], but more confusing:
```html
<script setup>
import { ref } from 'vue'
import ChildComp from './ChildComp.vue'

const msg = ref('from parent')
</script>

<template>
  <ChildComp>Message: {{ msg }}</ChildComp>
</template>
```

`ChildComp.vue`:
```html
<template>
  <slot>Fallback content</slot>
</template>
```

### #todo
Seems like you can do this:
```html
<span :class="{ done: todo.done }">{{ todo.text }}</span>
```
How? Why?
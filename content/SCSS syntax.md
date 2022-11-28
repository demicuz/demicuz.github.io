---
title: "SCSS syntax"
date: "2022-11-13"
---

### Nesting
```SCSS
content {
  ul {
    li {
      font-style:italic;
    }
  }
  ol {
    li {
      font-decoration:underline;
    }
  }
}
```

You can use `&` for referencing the topmost class:
```SCSS
button {
  background-color: #535353;
  color: #000;
  &:hover {
    background-color: #000;
    color: #fff;
  }
  &-cool {
    // selects .button-cool elements
  }
}
```
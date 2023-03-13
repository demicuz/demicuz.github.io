---
title: "Advanced C syntax"
date: "2022-11-29"
---
#tbd
Anonymous structs and enums! See [this video](https://www.youtube.com/watch?v=3PeTZb727mk).

### Designated initializers for aggregate types
Example from TreeSitter:
```C
static const TSSymbolMetadata ts_symbol_metadata[] = {
  [ts_builtin_sym_end] = {
    .visible = false,
    .named = true,
  },
  [aux_sym_content_token1] = {
    .visible = false,
    .named = false,
  },
  ...
};
```
Take a look [here](https://github.com/gbprod/tree-sitter-twig/blob/42f379e658b16b37804c72a1e30c9a4ccd81f52e/src/parser.c#L488) and [here](https://github.com/gbprod/tree-sitter-twig/blob/42f379e658b16b37804c72a1e30c9a4ccd81f52e/src/parser.c#L1095).

[Designated initializers for aggregate types - IBM Documentation](https://www.ibm.com/docs/en/zos/2.4.0?topic=initializers-designated-aggregate-types-c-only)

### Links
- [C11 features](https://smartbear.com/blog/c11-a-new-c-standard-aiming-at-safer-programming/)
- [Modern C for C++ Peeps](https://floooh.github.io/2019/09/27/modern-c-for-cpp-peeps.html)
---
title: "Clojure learning log"
date: "2022-09-04"
---

`'(1 2 3)` syntax to construct lists. a `'` basically means "don't interpret this as expression".

You can use `:a <map>` and `<map> :a` syntax to get a value out of a map. They have a slight difference, though I don't remember what exactly.

Seems like you can get nth element of a vector with this weird syntax:
```Clojure
([41 42 43 44] 2) ;; 43
```

### New cool functions
`iterate`
`peek`, `pop`
`lazy-seq`

`walk`, `tree-seq` - mind blown.

### 4Clojure
Custom flatten:
```clojure
(fn[x]  (filter (complement sequential?)
          (rest (tree-seq sequential? seq x))))
```

### Random syntax things
Not equal operator is `not=`, not `!=`. `!=` has some different meaning.
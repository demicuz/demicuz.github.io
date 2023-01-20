---
title: "Clojure learning log"
date: "2022-09-04"
---

`'(1 2 3)` syntax to construct lists. a `'` basically means "don't interpret this as an expression".

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

Transpose:
`apply mapv vector [[1 2 3] [41 42 43]] => [[1 41] [2 42] [3 43]]`

Can be used for Python vibes:
```clojure
(defn zip [& xs]  
  (apply map vector xs))
```

[Clojure Destructuring Tutorial and Cheat Sheet](https://gist.github.com/john2x/e1dca953548bfdfb9844)
[Recursively transform a nested map into transients, and then back to persistents](https://gist.github.com/devn/b195dbc67a320021057c)
Destructuring can shoot you in the foot. For example, this function works fine with a sequence of any length:
```clojure
(defn marker? [[a b c d]]  
  (not= a b c d))
```

This should be in the standard library:
```clojure
(defn in?   
  "true if coll contains elm"  
  [coll elm]    
  (some #(= elm %) coll))
```

[Find index of an element matching a predicate in Clojure? - Stack Overflow](https://stackoverflow.com/questions/8641305/)
[How to drop the nth item in a collection in Clojure? - Stack Overflow](https://stackoverflow.com/questions/24553524/)
[clojure - Returning duplicates in a sequence - Stack Overflow](https://stackoverflow.com/questions/8056645)

[Clojure Zippers](https://grishaev.me/en/clojure-zippers/)

`defpure` macro by [[Fred Overflow]].

Advent of Clerk repo has some cool code in the GitHub forks. Check out the Network.

[[Clerk#Examples]]

### Articles
- https://www.abhinavomprakash.com/posts/clojure-walk/
- [Clojure - Transient Data Structures](https://clojure.org/reference/transients)

### 4Clojure
Custom flatten:
```clojure
(fn[x]  (filter (complement sequential?)
          (rest (tree-seq sequential? seq x))))
```

### Random syntax things
Not equal operator is `not=`, not `!=`. `!=` has some different meaning.
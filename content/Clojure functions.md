---
title: "Clojure functions"
date: "2022-09-06"
lastmod: "2022-09-06"
---

`walk` example:
```Clojure
;; from -> clojuredocs
user=> (def c 5) user=> (-> c (+ 3) (/ 2) (- 1)) 3
;; and if you are curious why
user=> (use 'clojure.walk)
user=> (macroexpand-all '(-> c (+ 3) (/ 2) (- 1)))
(- (/ (+ c 3) 2) 1)
```

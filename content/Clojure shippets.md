---
title: "Clojure snippets"
date: "2022-09-06"
lastmod: "2022-09-06"
---

`(require '[clojure.string :as str])` for string stuff.

Instead of `:as` you could use `:refer` and then list some functions you want to import. It's kind of like `from bar import foo` in Python. `:refer :all` imports all of them.

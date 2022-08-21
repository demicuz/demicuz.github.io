---
title: "clangd"
date: "2022-08-17"
tags: [tool, util]
---

Provides IDE-like features for text editors through [[Language Server Protocol]]. Needs `compile_commands.json` for all the files to enable indexing and stuff. There are several ways to generate it. You can use `-MJ` flag with [[clang]] and concatenate the results into one file. Or use [Bear](https://github.com/rizsotto/Bear). Or [this Python thingie](https://github.com/nickdiego/compiledb).
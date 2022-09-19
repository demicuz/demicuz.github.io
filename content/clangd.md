---
title: "clangd"
date: "2022-08-17"
tags: [tool, util]
---

Provides IDE-like features for text editors through [[Language Server Protocol]]. Needs `compile_commands.json` for all the files to enable indexing and stuff. There are several ways to generate it. You can use `-MJ` flag with [[clang]] and concatenate the results into one file. Or use [Bear](https://github.com/rizsotto/Bear). Or [this Python thingie](https://github.com/nickdiego/compiledb).

### clang-tidy
You have to create `.clang-tidy` file in the project root directory and specify the checks you need ([list of options](https://clang.llvm.org/extra/clang-tidy/#using-clang-tidy)). Example:
```
Checks: 'bugprone-*,cert-*,clang-analyzer-*,concurrency-*'
```

- [clang-tidy in Visual Studio Code - YouTube](https://www.youtube.com/watch?v=8RSxQ8sluG0)
- [Configuration - clangd](https://clangd.llvm.org/config.html#clangtidy)
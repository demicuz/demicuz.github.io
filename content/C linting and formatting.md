---
title: "C linting and formatting"
---

You can use either `gcc` or `clang` for this, they come with static code analyzers. The flag `-fsyntax-only` prevents them from compiling object files, which may be useful (see [here](https://stackoverflow.com/questions/40105453/what-is-the-use-of-fsyntax-only-option-in-gcc-command/42940607)).

For formatting, there's ClangFormat ([can be used in Clion](https://www.jetbrains.com/help/clion/clangformat-as-alternative-formatter.html)).

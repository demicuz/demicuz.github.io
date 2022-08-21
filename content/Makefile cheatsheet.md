---
title: "Makefile cheatsheet"
date: "2022-08-18"
lastmod: "2022-08-18"
---

`all: main.c foo.c bar.c`
-   `$@`: The target (`all`).
-   `$%`: The filename element of an archive member specification.
-   `$<`: The filename of the first prerequisite (`main.c`).
-   `$?`: The names of all prerequisites that are newer than the target, separated by spaces.
-   `$^`: The filenames of all the prerequisites, separated by spaces (`main.c foo.c bar.c`). This list has duplicate filenames removed since for most uses, such as compiling, copying, etc., duplicates are not wanted.
-   `$+`: Similar to `$^`, this is the names of all the prerequisites separated by spaces, except that `$+` includes duplicates. This variable was created for specific situations such as arguments to linkers where duplicate values have meaning.
-   `$*`: The stem of the target filename. A stem is typically a filename without its suffix. Its use outside of pattern rules is discouraged.
- `$(@F)`: like `$(notdir $@)`

### Links
- [What do the makefile symbols $@ and $< mean? - Stack Overflow](https://stackoverflow.com/questions/3220277/what-do-the-makefile-symbols-and-mean) (has some useful info)
- [Automatic Variables (GNU make)](https://www.gnu.org/software/make/manual/html_node/Automatic-Variables.html)

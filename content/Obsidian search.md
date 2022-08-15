---
title: "Obsidian search"
date: "2022-08-14"
lastmod: "2022-08-14"
---

## Search syntax

### Combing sub-queries

When crafting a search query, remember that clicking "Explain Search Term" will give an explanation of what is being searched for, which can be very useful when debugging a complicated search.

- Words in the search query separated by space will be searched independently in each note. For example `foo bar` will find a note that includes both `foo` and `bar` anywhere in it.
- `"Quoted strings"` can be used to search multiple consecutive words separated by space, or in other words, a phrase. So, searching for `"foo bar"` with quotes will only find notes that include those words next to each other. You can use backslash `\"` to escape double quotes if you actually want to search for a string that includes quotes. And `\\` will do the same for backslash.
- Boolean operations can be used. Use `OR` to match one or another. Use `-` to negate a query. The space character is used for boolean "and".
	- For example: `foo OR bar` will find all notes that contain either of those words, they don't have to be in the same note. `foo -bar` will find all notes that contain `foo`, but not if they also contain `bar`.
- Parenthesis can be used to group boolean operations. For example `(a OR b) (c OR d)`. This can be useful when crafting complex searches to make sure things happen in the order you want.
- Regular expressions (regex) can now be used in search. Use forward slash to denote a regular expression. For example: `/[a-z]{3}/`.

### Search operators

Several special operators are available. Some operators allow nesting queries using parenthesis, for example: `file:("to be" OR -"2B")`.

- `file:` will perform the following subquery on the file name. For example: `file:".jpg"`. If you use Zettelkasten-style UIDs, this can be useful for narrowing a time range, for example `file:"202007"`for files created in July of 2020.
- `path:` will perform the following subquery on the file path, absolute from the root. For example: `path:"Daily Notes/2020-07"`.
- `match-case:` and `ignore-case:` will override the case sensitive match logic for the following subquery.
- `tag:` will search for your specified tag within a file, for example `tag:#work`. This is faster and more accurate than searching for the tag in plaintext `#work`, as it uses the cached information and ignores text in code blocks and sections that aren't markdown text.
- `line:(...)` will perform the subquery on a line-by-line basis, rather than a file-by-file basis. For example, if you search for `foo bar`, this could match a file that has `foo` in the first paragraph and `bar` in the last paragraph. Searching for `line:(foo bar)` will only match if `foo` and `bar` are on the same line.
- `block:(...)` will perform the subquery on a block-by-block basis, where each block defined as a markdown block, typically separated by empty lines. This is expensive computationally as it requires parsing each file, which means this is likely slower than other modes.
- `section:(...)` will perform the subquery on a section-by-section basis, where each section is the text between two headings, including the first heading.
- `content:(...)` will search file contents only

### Searching blocks and tasks
You can do it with `task:` or `block:`. There's also `task-todo:` and `task-done:`. Use `task:""` to match all tasks. More info [here](https://forum.obsidian.md/t/obsidian-release-v0-12-0/16809).
## Queries
The syntax is the same as in search. Example:
```query
file:2021-03
```

```note-imp
Queried pages don't show up in graph or backlinks
```

---
title: "VIM"
aliases: [neovim, nvim]
---

[[VIM vs Emacs]]

### To-do
Why do `cw` and `ce` act the same way, but `dw` and `de` not?
`Shift + d` seems to behave like `d$`. Why?

### Currently learning
`ge` - `e` but backwards
`o`, `O` - insert newlines
`A` - append to the end of the line
`\c` - escape char for case-insensitive search
`<C-y>`, `<C-e>` - scroll up/down

### Commands
`ge` - `e` but backwards
`U` - undo the whole line
`<C-r>` - redo
`p` - paste deleted text
`r_` - replace characters
`c` - change characters. `ce` - change all character until the end of the word.
`o`, `O` - insert newlines

`123 G` or `:123` - go to line 123
`<C-o>` - go back
`<C-i>` - go forward
`K` - quick docs on the word the cursor is on

`%` - to find matching parenthesis

`;`, `,` - repeats last ... Dunno what, but works with `f, t, F, t` commands
`.` - repeats last operation

`\c` - escape char for case-insensitive search

### File operaitons
`:e <path/to/file>` - open a file
`:saveas <path/to/file>` - save a file with a specified name

### Navigation
`H`, `M`, `L` - high, middle, low (faster than `hjkl`)
`zt`, `zz`, `zb` - same, but doesn't move the cursor

### Folds
The command `zc` will close a fold (if the cursor is in an open fold), and `zo` will open a fold (if the cursor is in a closed fold). It's easier to just use `za` which will toggle the current fold (close it if it was open, or open it if it was closed).

The commands `zc` (close), `zo` (open), and `za` (toggle) operate on one level of folding, at the cursor. The commands `zC`, `zO` and `zA` are similar, but operate on all folding levels (for example, the cursor line may be in an open fold, which is inside another open fold; typing `zC` would close all folds at the cursor).

The command `zr` reduces folding by opening one more level of folds throughout the whole buffer (the cursor position is not relevant). Use `zR` to open all folds.

The command `zm` gives more folding by closing one more level of folds throughout the whole buffer. Use `zM` to close all folds.

([link](https://vim.fandom.com/wiki/Folding))

### Smooth scrolling
Why that's not a thing in VIM? Fuck you, that's why. Or use [[neovide]].

See also:
- [How can I change the scroll wheel behavior in vim, so that it scrolls instead of moving the cursor?](https://superuser.com/questions/351972/)

### Useful
- [Simple .vimrc or init.vim for nvim (neovim)](https://gist.github.com/mendeza/e0c4fbb5592ad52f5eca77ed5873a46b)
- [Learn Vim Progressively](https://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)
- [scroll - How to move screen without moving cursor in Vim?](https://stackoverflow.com/questions/3458689)
- [5 cool terminal pagers in Fedora - Fedora Magazine](https://fedoramagazine.org/5-cool-terminal-pagers-in-fedora/)
- [How to make vim paste from (and copy to) system's clipboard?](https://stackoverflow.com/questions/11489428)

### Plugins
- [yuttie/comfortable-motion.vim](https://github.com/yuttie/comfortable-motion.vim) - smooth scrolling

---
title: "Sublime Text"
date: "2022-08-17"
lastmod: "2022-08-17"
---

- [[How Sublime Text was built]]
- [[Sublime Text key bindings]]

### Useful
- [Sublime tips for multi-cursor mastery](https://www.mediasuite.co.nz/blog/sublime-tips-multi-cursor-mastery/)
- [Multiple Selection with the Keyboard – Sublime Text Documentation](https://www.sublimetext.com/docs/multiple_selection_with_the_keyboard.html) #todo
- [lunixbochs/ActualVim: Sublime Text 3 input mode using Neovim.](https://github.com/lunixbochs/ActualVim) #todo
- Can I create a build system that launches [[kitty]]? Or even better, uses existing session?

### Disabling ligatures
In Sublime settings:
```json
"font_options": ["no_liga", "no_clig", "no_calt"]
```
Or just use a variation of the font without them.

### Notes
`View Package File` allows to view package files! Useful for viewing build systems.

#todo: do LSP completions conflict with standard Sublime completions and snippets, like EasyClangComplete's do? See also [Snippets not working as expected in 4107](https://github.com/sublimehq/sublime_text/issues/4254).

There are syntax-specific settings, which is nice.

#todo: Do per-project plugin settings completely override the default settings, or just the things that are changed are overriden?

### LSP
- [How to stop lsp-mode including headers automatically for C/C++ code?](https://emacs.stackexchange.com/questions/58015/)

```json
{
	"clients":
	{
		"clangd":
		{
			"enabled": true,
			"command": ["clangd", "--header-insertion=never"]
		}
	}
}
```

See also [[clangd]]
- [Customization - LSP for Sublime Text](https://lsp.sublimetext.io/customization/)

For Python, I installed LSP-pylsp **and** LSP-pyright. Used config from LSP-pylsp README.

### Vintage
- [tonymagro/VintageEscape: Closes the completion menu and exits insert mode when escape is pressed in Sublime Text vintage vim mode.](https://github.com/tonymagro/VintageEscape)

Tip: you can [override](https://www.sublimetext.com/docs/packages.html#overriding-files-from-a-zipped-package) default package stuff by creating your version of files in `sublime-text/Packages` folder. To edit `Default.sublime-keymap` for Vintage, create `Vintage` folder and place your version of `Default.sublime-keymap` in it.

### Links
- [C Function Parameter Hints](https://forum.sublimetext.com/t/c-function-parameter-hints/31156)
- [Sublime Build Systems - YouTube](https://www.youtube.com/playlist?list=PLGfKZJVuHW91WyVIitRhcTPD1PTFIPsia)
- [Chokidar-based file watcher implementation for LSP](https://github.com/sublimelsp/LSP-file-watcher-chokidar) #todo/coding 
- [Usage · rizsotto/Bear Wiki](https://github.com/rizsotto/Bear/wiki/Usage#build-tools)

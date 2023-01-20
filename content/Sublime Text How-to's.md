---
title: "Sublime Text How-to's"
date: "2022-12-02"
---

### Set default syntax for some extension
`View -> Syntax -> Open all with current extension as...`

### Disabling ligatures
In Sublime settings:
```json
"font_options": ["no_liga", "no_clig", "no_calt"]
```
Or just use a variation of the font without them.

### Per-project settings
Create a `.sublime-project` file in the root directory, add `"settings"` key to it:
```json
{
	"folders":
	[
		{
			"path": "."
		}
	],
	"settings":
    {
        "tab_size": 2
    },
}
```

The **User Interface Settings** and **Application Behavior Settings** are global to the entire application and can not be controlled by a syntax specific settings file, nor the `settings` key in a `.sublime-project`.

See also [reywood/sublime-project-specific-syntax](https://github.com/reywood/sublime-project-specific-syntax).
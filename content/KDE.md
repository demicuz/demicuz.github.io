---
title: "KDE"
date: "2022-10-21"
lastmod: "2022-10-21"
---

### Shortcuts
- Emoji picker - `meta + .`
- Processes - `Ctrl + Esc`
- `Alt + ~` - walk through windows of current app
- `Meta + Arrows` - tile windows
- `Fn + Meta + Up/Down` - maximize/minimize windows
- `Meta + Alt + Up/Down` - switch to window above/below
- `Meta + Shift + Up` - pin/unpin windows (added myself)
- `middle click on desktop` - paste to a Sticky Note
- `ctrl + alt + esc` - kill windows!! ☠
- Screenshots
	- Whole screen - `PrtSc` or `Shift + PrtSc`
	- Active window - `Super + PrtSc`
	- Region - `Super + Shift + PrtSc`

### Dolphin
- `Ctrl + H` - toggle hidden files

### Changes I've made
`Right Alt` was  a Compose key, removed this binding. Dunno what that key does anyway. `Caps Lock` is switching layouts. Someday I will remap `Caps Lock` to `Ctrl`, but now this thing acts weirdly. In Sublime, when I switch tabs with `Alt + Tab`, tab order is messed up. In terminals `Ctrl + Shift + W` doesn't work, unless you release `Shift` first.

**Unbind `Meta` key from application launcher**
Add this to `~/.config/kwinrc`:
```
[ModifierOnlyShortcuts]
Meta=
```
Yes, you **can't** do this through Shortcuts settings. [Source](https://superuser.com/a/1158462).

### Settings I tend to change
Make touchpad pointer faster, enable tap-to-click.

### Widgets
Click and hold to move around. It's really not that obvious.

### Links
- [Right Alt is AltGr in KDE. How can I make it behave the same as the left Alt?](https://askubuntu.com/questions/528481)

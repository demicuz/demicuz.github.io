---
title: "KDE settings I tend to change"
date: "2022-12-23"
---

### Desktop
Set UI scale to 125%.

Settings -> Window Management -> KWin Script -> enable "MinimizeAll"
Settings -> Shortcuts -> Shortcuts -> Kwin -> Set shortcut you want for "MinimizeAll" (default here was `Meta+Shift+D`)

Right click on this -> Show Alternatives -> Minimize all windows:
![](https://i.imgur.com/egQFusL.png)

RIght click on date -> configure digital clock -> change time display to 24h, date format to custom `ddd d`. I tried to change locales, but I remember that something somewhere crashed long time ago due to locale mishap (system language in one locale, date in another, money in another, etc). So I don't do that stuff anymore. The software is so fragile :)

Right click on the speaker icon -> Configure Audio Volume -> Don't play audio feedback on volume change.

[Add a key binding to center windows](https://askubuntu.com/questions/1219861/).

### Keys
Make `Caps Lock` another `Esc`. Unbind `Right Alt` from `Compose` key, don't know what it does anyway. Someday I will remap `Caps Lock` to `Ctrl`, but now this thing acts weirdly. In Sublime, when I switch tabs with `Ctrl+Tab`, tab order is messed up. In terminals `Ctrl+Shift+W` doesn't work, unless you release `Shift` first.

Set keyboard layout switching to `Ctrl+Alt+K`, show pop-up to `false`, "Switching policy" to "Application".

Unbind `Meta` key from application launcher. Add this to `~/.config/kwinrc`:
```
[ModifierOnlyShortcuts]
Meta=
```
No, you **can't** do this through Shortcuts settings. [Source](https://superuser.com/a/1158462).

Set key repeat delay to 250ms, repeat rate to 40, pointer acceleration to 0.2, tap to click. My `kcminputrc`:
```
[$Version]
update_info=delete_cursor_old_default_size.upd:DeleteCursorOldDefaultSize,kcminputrc_fix_botched_5_21_0.upd:kcminputrc_fix_botched_5_21_0_pre,kcmi>

[Keyboard]
RepeatDelay=250
RepeatRate=40

[Libinput][1267][12363][ELAN469D:00 04F3:304B Touchpad]
NaturalScroll=true
PointerAcceleration=0.200
TapToClick=true

[Mouse]
X11LibInputXAccelProfileFlat=false
XLbInptPointerAcceleration=0.2

[Tmp]
update_info=delete_cursor_old_default_size.upd:DeleteCursorOldDefaultSize
```

### Power management
Don't suspend session automatically when on battery. Disable screen locking and `Meta+L`.

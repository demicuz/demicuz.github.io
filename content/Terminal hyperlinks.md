---
title: "Terminal hyperlinks"
date: "2022-12-31"
---

### For [[Sublime Text]]
This magic script adds links to the `gcc` or `clang` output:
```shell
#!/bin/bash

# Without ANSI escape codes
# sed -e $'s#^\(.*\:[[:digit:]]\+:[[:digit:]]\+\)#\e]8;;subl:\/\/'`pwd`/$'\\1\a\\1\e]8;;\a#'

# With ANSI escape codes
sed -e $'s#^.*K\(.*\:[[:digit:]]\+:[[:digit:]]\+\)#\e]8;;subl:\/\/'`pwd`/$'\\1\a\\1\e]8;;\a#'
```

It will break if the ANSI escape codes formatting will be changed some day, but anyway. It also breaks formatting, too lazy to fix.

![](https://i.imgur.com/FaEjSVk.png)
`src/main.c:90:11` should be bold, but it's not.

Then you have to pipe `stderr` from the compiler to it, e.g. in [[fish]]:
```fish
make 2>| ./gcc-sublime-links
```

To keep colors from the compiler output, use `-fdiagnostics-color=always` flag with `gcc` or `clang`.

To open the links, you have to set up a custom `subl` protocol. No, I didn't come up with a better solution. How to do this: [xdg - Create a custom URL Protocol Handler](https://unix.stackexchange.com/questions/497146/).

Create a `.desktop` file in `~/.local/share/applications`:
```
[Desktop Entry]
Type=Application
Name=Subl Scheme Handler
Exec=subl-opener.sh %u
StartupNotify=false
MimeType=x-scheme-handler/subl;
```

Then run:
```shell
xdg-mime default subl-opener.desktop x-scheme-handler/subl
```

This adds an entry to `~/.config/mimeapps.list`. And does something else maybe, because simply removing `subl` from that file and rebooting didn't remove the protocol handler from the system. Meh.

The script (`subl-opener.sh`):
```shell
#!/usr/bin/env bash

subl ${1#subl://}

# if [[ "$1" == "subl:"* ]]; then
    #ref=$(python -c "import sys, urllib as ul; print ul.unquote_plus(sys.argv[1])" "$ref") # If you want decoding
    # subl ${1#subl://}
# else
    # xdg-open "$1" # Just open with the default handler
# fi
```

Only one issue left - `xdg-open` is slow on my laptop. The `subl` command by itself is very fast. Sigh.

```
________________________________________________________
Executed in  268.41 millis    fish           external
   usr time  157.60 millis    0.00 micros  157.60 millis
   sys time   82.13 millis  887.00 micros   81.25 millis
```

#### kitty
If you use [[kitty]], you don't have to deal with `xdg-open`, just add this to [`open-actions.conf`](https://sw.kovidgoyal.net/kitty/open_actions/):
```
protocol subl
action launch --type=background /usr/bin/subl $FILE_PATH
```

Kitty checks it first, so it doesn't use `xdg-open`. The downside is that it's also a bit slow. But faster than `xdg-open`!

### Links
- [Create clickable links in terminal](https://unix.stackexchange.com/questions/112267/)
- [Creating a hyperlink from command line output on a terminal](https://askubuntu.com/questions/1391071/)
- [Scripting the mouse click - kitty](https://sw.kovidgoyal.net/kitty/open_actions/)
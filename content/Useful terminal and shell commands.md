---
title: "Useful terminal and shell commands"
---

- [[Terminal tools]]

### Misc (Shell)
`wc` - count words, lines, etc.
`less` - read smth long in terminal instead of printing it
`gunzip file.gz` - unzip gzipped files
`ls -R` - recursively list files
`whereis/which` - where is a certain program
`hexdump` - show bytes. `hexdump -vC` is handy.

### Other
[[awk]] - execute data queries
[[cut]] - awk na minimalkah
[[grep]] - search for a particular text
[[Managing users in Linux#Commands]]

### Tips
- `ctrl + r` - search history. You can also use `history`
- `ctrl + a` - beginning of a line
- `ctrl + e` - end of a line
- `ctrl + w` - delete a word
- `ctrl + u` - delete whole command
- `ctrl + l` - clear screen
- `!!` - last executed command. Forgot `sudo`? Use `sudo !!`. Doesn't work in [[fish]].
- `convert file.{jpg,png} => convert file.jpg file.png`
- `cd -` - go to last visited folder
- `pushd, popd` - alternative to `cd`, uses stack
- `<( )` - process substitution, treat output like a file (no more temporary files): `diff <(ls) <(ls -a)`

##### Links
- [more bash tricks](https://wizardzines.com/comics/more-bash-tricks/)

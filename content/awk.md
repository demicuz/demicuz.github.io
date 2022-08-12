---
title: "awk"
---

Smth like UNIX [[SQL]]. Yup, it's a whole language.
##### Links
- [How to Use the awk Command on Linux](https://www.howtogeek.com/562941/how-to-use-the-awk-command-on-linux/)
##### Examples
Print the third column of a space-separated file:
```bash
awk '{print $3}' tables.txt
```
Print the last column of each line in a file, using a comma as a field separator:
```bash
awk -F ',' '{print $NF}' tables.txt
```
Print lines that match a condition:
```bash
awk '($10 >= min_value && $10 <= max_value)' tables.txt
```
Print first, second and last arguments:
```bash
awk '{print $1,$2,$NF}' some_text.txt
```
##### Flags
- `-F` - set field separator
##### Variables
- `RS` - record separator (think "line separator"), `\n` by default
- `FS` - field separator, space by default
- `NF` - number of fields read
- `FNR` - current record number in **FILENAME**
- `NR` - current record number in the total input stream

##### Other info
> Records are read one at a time, and stored in the field variable `$0`. The record is split into fields which are stored in `$1`, `$2`, ..., `$NF`.

> Data input stored in fields is string, unless the entire field has numeric form and then the type is number and string.

So you can treat it like both:
```bash
echo 24 24E | mawk '{ print($1>100, $1>"100", $2>100, $2>"100") }'
0 1 1 1
```

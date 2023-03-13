---
title: "Black Python formatter"
date: "2023-02-18"
---

> _Black_ reformats entire files in place. It doesn’t reformat lines that end with `# fmt: skip` or blocks that start with `# fmt: off` and end with `# fmt: on`. `# fmt: on/off` must be on the same level of indentation and in the same block, meaning no unindents beyond the initial indentation level between them. It also recognizes [YAPF](https://github.com/google/yapf)’s block comments to the same effect, as a courtesy for straddling code.

> **The magic trailing comma**
> _Black_ in general does not take existing formatting into account.
>
> However, there are cases where you put a short collection or function call in your code but you anticipate it will grow in the future.
>
> For example:
> ```python
> TRANSLATIONS = {
>     "en_us": "English (US)",
>     "pl_pl": "polski",
> }
> ```
> 
> Early versions of _Black_ used to ruthlessly collapse those into one line (it fits!). Now, you can communicate that you don’t want that by putting a trailing comma in the collection yourself. When you do, _Black_ will know to always explode your collection into one item per line.
>
> How do you make it stop? Just delete that trailing comma and _Black_ will collapse your collection into one line if it fits.

### Related
- [[Code formatting]]

### Links
- [The Black code style](https://black.readthedocs.io/en/stable/the_black_code_style/current_style.html)

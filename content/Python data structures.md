---
title: "Python data structures"
date: "2023-02-18"
---

### `@dataclass`
A glorified `struct`. See [Data Classes – Real Python](https://realpython.com/python-data-classes/), has a lot of useful info.

You can do stuff like this:
```Python
from dataclasses import dataclass, field
from typing import List

@dataclass
class Deck:
    cards: List[PlayingCard] = field(default_factory=make_french_deck)
```

Avoids "mutable defaults" problem.

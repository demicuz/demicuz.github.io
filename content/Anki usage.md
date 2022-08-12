---
title: "Anki usage"
---

*I need to further explore this...*

### General principles
Everything is a note. A card uses templates for front and back sides. You can, for example, flip those by going to `Edit card -> Cards -> Flip`.

Anki uses `::` to show different deck levels. A deck called `Chinese::Hanzi` refers to a "Hanzi" deck, which is part of a "Chinese" deck.

### Cloze
Choose type "cloze" and use `{{c1::Hi, I'm cloze}}` syntax. The `c1` part means that you’ve created one cloze deletion on the sentence.
`{{c2::Canberra}} was founded in {{c1::1913}}.` creates two cards. The first one is `Canberra was founded in [...].` and the second is `[...] was founded in 1913.`.

For more tricks, like adding hints, etc, see [the docs](https://docs.ankiweb.net/editing.html#cloze-deletion).

### Hotkeys
- `Ctrl + enter` - add note to your collection

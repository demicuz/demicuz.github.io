---
title: "Quartz"
---

Publish your brain! [[HUGO]] goes brr.

### Progress
I should write a script that updates all the notes correctly. It should:

**Generate the list of notes to be updated**
Look at all the notes last update time and compare it to those on the website. If they're newer or don't exist on the website, then add those to the "pool". Remove from pool notes that don't have `publish: true`.

**Update each note**
Add correct `title` and `lastmod` fields to metadata. If a note has h1 heading, remove it.

### Stuff to change
Tags are capitalized 😡😡😡

Tags with `-` are rendered weird. If viewed on a page, `-` is a space. So `ducks-swim` becomes `Ducks swim`. But when clicked, it's `Ducks-Swim`. Annoying. Also `ducks/swim` becomes `Ducks swim` when viewed on a page and `Ducks/Swim` when clicked.

Last modified date. Either remove it, or add `lastmod` to metadata.

### Links
https://quartz.jzhao.xyz/

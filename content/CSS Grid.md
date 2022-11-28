---
title: "CSS Grid"
date: "2022-09-28"
---

Like [[Flexbox]], but two-dimensional. Allows to create complex layouts. Somehow adds additional syntax, which doesn't have any logic:
- Positioning items adds `/` (**not** division) and has **two** different meanings!
- Template areas add markdown-like syntax for naming areas
- Naming lines adds `[]`
- `fr` unit. Wat. Flexbox grow/shrink is basically the same thing, but it doesn't use `fr`.
- `span` keyword. Has nothing in to do with HTML `<span>`. `span 2` means "take up 2 cells".

`display: grid` and there you go.

### Terminology[^1]
**Grid lines** - lines that divide columns and rows.
**Grid cell** - a single unit of a grid
**Grid area** - rectangular space surrounded by four grid lines
**Grid track** - space between two grid lines
**Grid row** - horizontal track of a grid
**Grid column** - vertical track of a grid

### Properties
`grid-template-rows`, `grid-template-columns`
Set sizes of grid rows and columns. Could be in `px`, `%`, etc, or in special unit `fr` (fraction). You can mix those:
```
grid-template-columns: 10rem 30% 1fr;
```

`grid-auto-rows`, `grid-auto-columns`
Set sizes for rows/columns that overflow the template layout.

`grid-row`, `grid-column`[^2]
For positioning grid items, like this:
```CSS
.item1 {
  grid-row-start: 2;
  grid-row-end: 3;
  grid-column-start: 2;
  grid-column-end: 3;
}
/*or: */
.item1 {
  grid-row: 2 / 3;
  grid-column: 2 / 3;
}
```
Yes, the second way syntactically looks like division.

See also [[#Named template areas]].

### Functions
`repeat()` - a special Grid function to represent a recurring pattern of rows or columns. E.g. `repeat(4, 10rem)` - `10rem 10rem 10rem 10rem`.

`minmax()` - the name says it all. Useful for setting minimum and maximum row/col size, like `minmax(10rem, auto)`.

### Named template areas
```CSS
.grid-container {
	display: grid;
	grid-auto-rows: minmax(5rem, auto);
	grid-template-columns: 1fr 20rem;

	grid-gap: 1rem;

	grid-template-areas: "header header"
						 "content sidebar"
						 "footer footer";
}

.grid-header {
	grid-area: header;
}

// And so on
```

### Auto-filling and auto-fitting tracks
```CSS
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, 100px);
    grid-gap: 20px;
}
```



### Links
- [Learn CSS Grid](https://learncssgrid.com/)
- [CSS Grid PlayGround | Mozilla](https://mozilladevelopers.github.io/playground/css-grid/)
- [Layout Land - YouTube](https://www.youtube.com/c/LayoutLand)
- [Grid by Example](https://gridbyexample.com/)
- [A simple visual cheatsheet](https://grid.malven.co/)

[^1]: [CSS Grid Terminology](https://mozilladevelopers.github.io/playground/css-grid/)
[^2]: [CSS Grid Position Items](https://mozilladevelopers.github.io/playground/css-grid/06-position-items)
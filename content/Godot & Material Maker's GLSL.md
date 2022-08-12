---
title: "Godot & Material Maker's GLSL.md"
---

### Weird functions that are included by default
- `rand`, `rand2`, `rand3`
- `hsv2rgb`, `rgb2hsv`

### Variables
- `$uv`
	- Values go from 0 to 1. The Y axis goes *down*.
- `$name-uv`
	- From the docs:
	> Since a node can be sampled for several different UV expressions in the same combined shader, it is necessary for all variables declared in the main code section to have a unique name for each (node instance, UV expression) pair. Material Maker provides the `name-uv` implicit variable for this.
- `$seed`
- `$time`
- `$name`
	- From the docs:
	>Instance functions must also have a unique name, and the name implicit variable can be used to do this: whenever `$name` or `$(name)` is used, it will be replaced with a unique name that depends on the node instance.

### Data types
- `bvec3` - see [[GLSL#^c28a06]]. Used in `sdPolygon`.

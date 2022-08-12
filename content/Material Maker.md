---
title: "Material Maker"
tags: [tool, graphics]
---

A program used to create shader materials for games (mainly for games). Its node-based approach allows to quickly put up some cool-looking thing. But lack of animation knobs makes it difficult to produce animations. I believe I can create custom nodes to compensate for this.

### To discover
- [[Godot & Material Maker's GLSL]]
- Can I just paste [[Shadertoy]] code directly into Global functions?
- Port groups (those blue buttons)
- [[Developing an iterator node for Material Maker]]

### Tips
#### Tricks
- You can use node's parameters when setting its parameters. [Example](https://pastebin.com/raw/dxJ40rbd). There, `$scale_y` is set to a complicated function. And then `$scale_x` is set to `$scale_y`.
- A trick with labels - if you type a number and a `:` in the beginning of the label, it will position it to the according row. See `Math` node for example.

#### Variables
`$time` - gets time. Can be used for animating variables.

To use a parameter in your shader code it is necessary to prefix it with a dollar sign. So a foo parameter can be referred to by `$foo` or `$(foo)` in the shader code. Gradient parameters need to be used as functions with a single float parameter. So `mygradient` should be referred to as `$mygradient($uv.x)` if you want to spread the gradient on the x axis (`$uv` is an implicit variable used by Material Maker for UV coordinates).

`$uv` can have more than two dimensions. SDF nodes rely on that.

#### Nodes
Nodes that provide random patterns have an implicit *seed* parameter. It is not possible to edit it directly, but moving the node in the graph will change its value. It is possible to freeze the seed value using the small dice button in the node’s title bar in the graph.

##### Input types
- V4->V4 takes `vec4` as input and returns `vec4` (while RGBA takes `vec2`)
- SDF3D-C is vec3->vec2 (position -> distance + color index)

##### Inputs and Instance functions
The “Function” checkbox changes the way the code is generated for this input. When set to true, the input is generated as a function and can be used in the `Instance functions` section. If the parameter is false, the input code is inlined. It is not advised to set this parameter to true when not required, because generating functions can have an impact on performance. ^fc1fdc

In shader code, **inputs** are used as **functions** that take a single `vec2` parameter. For example `$myinput(2.0*$uv+vec2(0.2, 0.3))` refers to `myinput`, scaled and translated.

##### Global functions
The Global functions tab is used to define the functions that are necessary to implement the texture generator. Those functions will be included only once (when the node is used of course) and **cannot** use parameters or inputs. This is typically where you will paste the code you prepared in Shadertoy. But they can use Instance functions! And Instance functions can take inputs.

##### Label tricks
You can use `n:` in Labels to set the position of a parameter. See `blend` node for example of that.

#### Reference panel
You can drag and drop colors everywhere!

### Useful articles and tutorials
- [Creating custom shader generators](https://rodzilla.itch.io/material-maker/devlog/106374/creating-custom-shader-generators-with-material-maker)
- [[Intro seminar to Material Maker]] by [[Paulo Falcao]]

### Pitfalls
When editing your custom nodes, ensure to save a *copy* of them, as it might break previous graphs using the older version of those nodes. I still don't understand how your custom nodes are stored in a  `.ptex` file. See [this doc page](https://rodzill4.github.io/material-maker/doc/nodes_common.html).

Also you can't leave comments in the Main Code section.

---
title: "Shadertoy"
---

A gold mine of really good fragment shaders.

### Resources
- https://shadertoyunofficial.wordpress.com/ - lots of cool stuff

### Current shaders I'm breaking down
- [Fractal tree](https://www.shadertoy.com/view/XtyGDR) by EvilRyu

### Accounts of some cool guys
- Nimitz (stormoid)
- [Shane](https://www.shadertoy.com/user/Shane/)
- [Paulo Falcao](https://www.shadertoy.com/user/PauloFalcao)
- Kali
- [flockaroo](https://www.shadertoy.com/user/flockaroo)
- [Evvvvil](https://www.shadertoy.com/user/Evvvvil)
- [Flopine](https://www.shadertoy.com/user/Flopine)
- [Nusan](https://www.shadertoy.com/user/Nusan)
- [BigWings](https://www.shadertoy.com/user/BigWings) aka The Art of Code
- [knighty](https://www.shadertoy.com/user/knighty/) - many mathy things!

### Pitfalls
- [[Shadertoy mysterious bugs]]
- ANGLE can ruin many things. See [this](https://www.shadertoy.com/view/wdVyWD), for example. But I'm not sure if disabling ANGLE is a good idea.
- [This guy](https://www.shadertoy.com/user/FabriceNeyret2/sort=newest) has a lot of examples of precision errors.
- Don’t ask for the angle of a null vector. => atan(y,x+1e-15) ([source](https://shadertoyunofficial.wordpress.com/2016/07/22/compatibility-issues-in-shadertoy-webglsl/)). But for coordinates it should be fine, as `gl_FragCoord` is always fractional.
- Complex expressions including redefinition of variables ( e.g., x = (x=y)*x ) may not be evaluate in the same order on some systems (typically, after translation to HLSL by Windows Angle; API drivers can also have problems), or can even be bugged (O += x -O on some old systems).  (OpenGL is wrongly evaluating first all the subdefinitions while here Angle is right.) For wide compatibility, avoid reusing the same variable redefinition within a single expression – which span includes comma-separated expressions.
- there are different bugs in OpenGL... ;-/ ( e.g. on very big arrays ) ([source](https://www.shadertoy.com/view/wtV3DW))

**Always** define your variables!

### Useful
- [Python program to render Shadertoys](https://github.com/danilw/shadertoy-to-video-with-FBO)
- [How to adapt iterative shaders to the power of the computer](https://www.shadertoy.com/view/tt3BRr)
- [Set shader as a website background](https://xemantic.github.io/shader-web-background/)

### Related
- [[Raymarching and SDFs]]
- [[Techniques in Shadertoy and shaders]]

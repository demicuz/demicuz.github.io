---
title: "Colors"
---

### GLSL

They're just plain RGB. They're linear. It's good for manipulating them, but not so good for the human perception. See [Computer Color is Broken](https://www.youtube.com/watch?v=LKnqECcg6Gw) video by [[Minute Physics]] and [this](https://www.shadertoy.com/view/lscSzl) shadertoy for examples of artifacts. See also [[Programming tricks in Shadertoy GLSL|this]] article, "Managing colors" section.

Before returning the final color, you should apply gamma correction to it (usually 2.2) or convert it to [[sRGB color space]], which most monitors use. See [this](https://www.shadertoy.com/view/lsd3zN) shadertoy which compares all 3 ways.

Also note that texture colors are also stored in sRGB, so when you fetch them, you (ideally) should convert them to linear RGB before any manipulation. Example: `col = pow(tex,vec4(2.2))`.

### Useful
- [Oklab color space](https://bottosson.github.io/posts/oklab/) and [example by iq](https://www.shadertoy.com/view/ttcyRS)

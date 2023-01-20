---
title: "3D viewer v1.0"
date: "2022-11-19"
---

### #todo
What are precompiled headers?
Choosing a GUI library: [[ImGui]] looks fine. Also [[Nuklear]]. Qt is too complex for this.

### Notes from the subject
> Таким образом при использовании структурного стиля получается, что программа строится в виде "слоеного пирога" сверху вниз. Ошибки генерируются на нижних уровнях и прокидываются на самый верх, где выводятся пользователю.

Сомнительный паттерн, но ок.

Use `gcc`, C11 standard.

### Unit testing
[`libcheck`](https://github.com/libcheck/check) is a library for unit testing.

### Random
Should use `glPolygonMode( GL_FRONT_AND_BACK, GL_LINE );` for rendering the wireframe.
`glfwSwapInterval(1)` for vsync

### Links
- [cimgui](https://github.com/cimgui/cimgui)

**Examples**
- [SolutionOP/3D\_Viewer\_C: Implementation of 3DViewer v1.0.](https://github.com/SolutionOP/3D_Viewer_C)
- [iayako/3DViewer-v2.0](https://github.com/iayako/3DViewer-v2.0)

**Various OpenGL stuff**
- [Урок 2. Отображение полигонов](https://pmg.org.ru/nehe/nehe02.htm)
- [opengl - How to render the wireframe of a cube without the diagonals on the faces](https://computergraphics.stackexchange.com/questions/1664/)
- [Wireframes on fragment shaders](https://wunkolo.github.io/post/2022/07/gl_ext_fragment_shader_barycentric-wireframe/) - it's for [[Vulkan]] though
- [Wireframes with barycentric coordinates](https://tchayen.github.io/posts/wireframes-with-barycentric-coordinates)
- [Drawing Lines is Hard](https://mattdesl.svbtle.com/drawing-lines-is-hard)
- [mhalber/Lines: 6 different implementations of doing wide line rendering in OpenGL](https://github.com/mhalber/Lines)

**Probably use this to draw lines**
[Draw different length of LINE\_LOOPs from buffer](https://stackoverflow.com/questions/23907881/)
[glMultiDrawElements](https://stackoverflow.com/questions/24516993/)

**Math**
- [coreh/gl-matrix.c](https://github.com/coreh/gl-matrix.c)
- [recp/cglm: 📽 Highly Optimized Graphics Math (glm) for C](https://github.com/recp/cglm)
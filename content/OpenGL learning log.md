---
title: "OpenGL learning log"
date: "2022-12-28"
---

### Vertex buffer object (VBO)
Create a buffer, set its id to `vbo`:
```C
GLuint vbo;
glGenBuffers(1, &vbo); // Generate 1 buffer
```

Then we need to **activate** the buffer:
```C
glBindBuffer(GL_ARRAY_BUFFER, vbo);
```

And then send the data to the GPU:
```C
glBufferData(GL_ARRAY_BUFFER, sizeof(vertices), vertices, GL_STATIC_DRAW);
```

Notice that this function doesn't refer to the id of our VBO, but instead to the **active array buffer**.

### Shaders
Example of vertex shader creation:
```C
GLuint vertexShader = glCreateShader(GL_VERTEX_SHADER);
glShaderSource(vertexShader, 1, &vertexShaderSource, NULL);
glCompileShader(vertexShader);
```
Unlike VBOs, you can simply pass a reference to shader functions instead of making it active or anything like that.

There are also some magic spells to check for compilation errors. See [[OpenGL#Templates]].

Then you have to create a program:
```C
GLuint shaderProgram = glCreateProgram();
glAttachShader(shaderProgram, vertexShader);
glAttachShader(shaderProgram, fragmentShader);
glLinkProgram(shaderProgram);
```

And use it:
```C
glUseProgram(shaderProgram);
```

Just like a vertex buffer, only one program can be active at a time.

### Attribute pointers
After sending the vertex data to the GPU, we should specify how to interpret it:
```C
GLint posAttrib = glGetAttribLocation(shaderProgram, "aPos");
glVertexAttribPointer(posAttrib, 3, GL_FLOAT, GL_FALSE, 0, NULL);
glEnableVertexAttribArray(posAttrib);
```
Google that up :)
A good explanation can be found here: [OpenGL - Drawing polygons](https://open.gl/drawing).

### Vertex array object (VAO)

![](https://i.imgur.com/oUyrRvR.png)

Creating (you should do it **before** creating and binding any VBO's):
```C
GLuint vao;
glGenVertexArrays(1, &vao);
```

Using:
```C
glBindVertexArray(vao);
```

### Element buffer objects (EBO)
Sort of a "view" into a VBO. A single vertex can be used multiple times. The reason is that vertices often overlap and it's cheaper to use indices instead of duplicating vertices.
```C
GLuint ebo;
glGenBuffers(1, &ebo);
```

```C
glBindBuffer(GL_ELEMENT_ARRAY_BUFFER, ebo);
glBufferData(GL_ELEMENT_ARRAY_BUFFER, sizeof(indices), indices, GL_STATIC_DRAW);
```
The index buffer binding is **stored within the VAO**.

### Various functions
`glDrawArrays` - draw stuff stored in VAO's.
It will use the **most recently bound** vertex array, and the **most recently used** shader program to draw. If we want to draw a different set of buffers, then we need to bind that before drawing again. If no valid buffer or shader has been set in the state machine then it will crash.

`glDrawBuffers` - huh? Probably for VBO's.
`glDrawElements` - I think it's for EBO's.

`glGetError` - if something goes wrong, returns the error code.

### #todo
![](https://i.imgur.com/nRFykxM.png)

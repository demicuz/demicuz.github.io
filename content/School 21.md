---
title: "School 21"
date: "2022-08-21"
lastmod: "2022-08-21"
---

### Useful pages
- [[C (language)]]
- [[MiniLibX]]

### Sber
- [[3D viewer v1.0]]
- [[SimpleNavigator v1.0]]
- [[Linux Monitoring]]
**Cool examples**
- [bezlant (Anthony)](https://github.com/bezlant)

Implementation of the _s21_graph_algorithms.h_ library:  
* The library must be developed in C++ language of C++17 standard
* The library code must be located in the src folder in the develop branch  
* Make it as a static library (with the _s21_graph_algorithms.h_ header file)
* The library must be represented as a ` GraphAlgorithms ` class that stores the implementation of algorithms on graphs. The class `GraphAlgorithms` itself must not know anything about the internal representation of the graph from the class `Graph`. To interact with graph data, the class `GraphAlgorithms` can only use the public methods and properties provided by the `Graph` class. 
* Add to the Makefile _s21_graph_algorithms.a_ target 
*Prepare full coverage of the `GraphAlgorithms` class methods with unit-tests
* The class ` GraphAlgorithms ` must contain at least the following public methods:
    + `depthFirstSearch(Graph &graph, int startVertex)` - a *non-recursive* depth-first search in the graph from a given vertex. The function should return an array that contains the traversed vertices in the order they were traversed. When implementing this function, you must use the *self-written* data structure **stack**, which should be previously made as a separate static library
    + `breadthFirstSearch(Graph &graph, int startVertex)` - breadth-first search in the graph from a given vertex. The function should return an array that contains the traversed vertices in the order they were traversed. When implementing this function, you must use the *self-written* data structure **queue**, which should be previously made as a separate static library
* It is necessary to use *self-written* helper classes `Stack` and `Queue` (you can reuse your solution from the *CPP2* project for this). These classes must contain the following methods:
    + `init()` - creating an empty stack/queue
    + `push(value)` - adding an element to the stack/queue
    + `pop()` - getting an element from the stack/queue followed by its removal from the stack/queue
    + `peek()` - getting an element from the stack/queue without its removal from the stack/queue

*In this and the following tasks, consider that the vertex numbers start from 1*]]

### Common core projects
- [[libft]]
- [[get_next_line]]
- [[born2beroot]]
- [[printf]]
- [[push_swap]]
- [[fract-ol]]
- [[Fdf]] (haven't done)
- [[minitalk]] (haven't done)
- [[pipex]]
- [[Philosophers]]
- [[minishell]] (in progress)

##### Future
- [[miniRT]]
- [[Cube3D]]

### Links
- [Rating 21](http://42stats.ru/)
- [Калькулятор уровней для Школы 21](https://calc21.ru/) (seems to be dead)
- [42evaluators](https://42evaluators.com/calculator)
- [mharriso/school21-checklists](https://github.com/mharriso/school21-checklists)

### Cool guys
- [mtiesha](https://profile.intra.42.fr/users/mtiesha)
- [acristin](https://profile.intra.42.fr/users/acristin)
- [Artem (Artyom) Kornikov | LinkedIn](https://www.linkedin.com/in/artyom-kornikov/) aka ngragas  ^3er3oh2
	- [Rush-iam/Hypernull-Bot-nGragas: Бот на соревнование Croc (занял 1 место)](https://github.com/Rush-iam/Hypernull-Bot-nGragas)
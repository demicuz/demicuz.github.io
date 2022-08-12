---
title: "printf"
---

A [[School 21]] project.

### Useful
- Testers
	- [paulo-santana/ft_printf_tester](https://github.com/paulo-santana/ft_printf_tester)
	- [Tripouille/printfTester](https://github.com/Tripouille/printfTester)
- Misc
	- [<stdarg.h>](https://pubs.opengroup.org/onlinepubs/007904975/basedefs/stdarg.h.html)
	- [stdarg.h - Wikipedia](https://en.wikipedia.org/wiki/Stdarg.h)
- [[Building C#Libraries]]
- [Пилим printf() своими руками. Часть первая. | by Weston Normcore | Medium](https://medium.com/@wnormcor/%D0%BF%D0%B8%D0%BB%D0%B8%D0%BC-printf-%D1%81%D0%B2%D0%BE%D0%B8%D0%BC%D0%B8-%D1%80%D1%83%D0%BA%D0%B0%D0%BC%D0%B8-5755cfbaf4e9)
	- > Важное отступление: чтобы считать аргумент типа char, нужно передать в **va_arg** тип **int**. Особенностей реализации мы здесь касаться не будем, просто запомните, что **char** считывается через **int**. [More info](https://stackoverflow.com/questions/28054194/char-type-in-va-arg).

Return value of built-in `printf` is the number of characters printed (returned). If an error occurred, the value is negative.

### To-do
- Ensure that functions from `libft` don't leak into `printf`. UPD: that's kinda impossible under Norminette and subject constraints.

### Notes
Variadic functions in C are dangerous. In case of type mismatch or wrong number of arguments the program crashes. See [this](https://stackoverflow.com/questions/3555583) and [this](https://stackoverflow.com/questions/205529) questions on [[Stack Overflow]].

In case of too many (or to few) arguments, passed to the built-in printf, a warning is raised. Though with flags `-Wall -Werror -Wextra` it won't even compile. In case of argument type mismatch, I think the behavior is undefined.

![[Pointers in C#^96aaca]]

#### Things from `man 3 printf`
The format string is  composed of zero or more directives: ordinary characters (not `%`), which are copied unchanged to the output stream; and conversion specifications, each of which results in fetching zero or more subsequent arguments.  Each conversion specification is introduced by the  character `%`, and ends with a *conversion specifier*.  In between there may be (in this order) zero or more  `flags`,  an  optional  `minimum  field  width`,  an optional `precision` and an optional `length` modifier.

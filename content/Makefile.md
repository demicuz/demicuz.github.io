---
title: "Makefile"
date: "2022-08-17"
lastmod: "2022-08-17"
---

GNU build thingie for C language. #todo one template to rule them all.

### Useful
- https://github.com/pyos/re2jit-template/blob/master/Makefile #todo
- [How to write a Makefile](https://github.com/amjadmajid/Makefile)
- [[Makefile cheatsheet]]
- [c++ - How to write a Makefile with separate source and header directories?](https://stackoverflow.com/questions/30573481/)
- [[Managing Projects with GNU Make]] - a whole book about Makefile (YES)
- [How to write a Makefile with separate source and header directories?](https://stackoverflow.com/questions/30573481/)
- [Rules of Makefiles | GNU make](https://make.mad-scientist.net/papers/rules-of-makefiles)
- [Auto-Dependency Generation | GNU make](https://make.mad-scientist.net/papers/advanced-auto-dependency-generation/)
- [Symbol "|" in dependency](https://stackoverflow.com/questions/52821513/)

### Related
- [[C debugging, compilation and building]]

### Notes
There are [implicit variables](https://stackoverflow.com/questions/11394659/) and rules, use `make -p -f /dev/null` to print them.
For compiling C++ use `CXX` instead of `CC`, `CXXFLAGS` instead of `CFLAGS`.

Suffix rules [ignore](https://www.gnu.org/software/make/manual/html_node/Error-Messages.html) prerequisites. So you can't write something like:
```Makefile
.c.o: $(HEADER)
	<your compilation steps>
```
But it seems like you can do this instead:
```Makefile
%.o: %.c $(HEADER)
	<your compilation steps>
```

There's also a thing called ".d files", which... Like an intermediate file format for Make, I guess? [what is .d file after building with make - Stack Overflow](https://stackoverflow.com/questions/19114410/what-is-d-file-after-building-with-make)

### `basename` function
It's **not** like `/usr/bin/basename`. It takes a path and strips away file extention. So `foo/bar.txt` becomes `foo/bar`. Use `$(notdir foo/bar.txt)` to get `bar.txt`. Yes, this is fucked up.

### Change file extensions
Use `$(SRC:.c=.o)` syntax. `SRC` is a list of files, separated by space.
[How to change the extension of each file in a list with multiple extensions in GNU make?](https://stackoverflow.com/questions/12069457/)

### vpath
Tell `make` where exactly to search for files. Probably archaic, like many things in Make.
 
### Examples
##### fract-ol
`-MMD -MP` so that the compiler creates `.d` files. They're needed for automatic header dependency generation. On the last line we include them in our Makefile.
```Makefile
NAME		:= fract-ol

SRC_DIR		:= src
OBJ_DIR		:= obj
LIB_DIR		:= lib

LIBFT_DIR	:= libft
MLX_DIR		:= minilibx-linux

LIBFT		:= $(LIB_DIR)/libft.a
LIBMLX		:= $(LIB_DIR)/libmlx.a

SRC_FILES	:= complex.c float_parser.c graphics_utils.c julia.c keyboard.c \
               main.c mandelbrot.c mouse.c ship.c
SRC			:= $(addprefix $(SRC_DIR)/, $(SRC_FILES))
OBJ			:= $(SRC:$(SRC_DIR)/%.c=$(OBJ_DIR)/%.o)

CC			:= cc
CPPFLAGS	:= -I include -I $(LIBFT_DIR) -I $(MLX_DIR) -MMD -MP
CFLAGS		:= -O3 -Wall -Werror -Wextra
LDFLAGS		:= -L$(LIB_DIR)
LDLIBS		:= -lft -lmlx -lXext -lX11 -lm -lz

.PHONY:	all bonus clean fclean re

all: $(NAME)

bonus: $(NAME)

$(LIBFT): $(LIB_DIR)
	$(MAKE) --directory=$(LIBFT_DIR)
	cp $(LIBFT_DIR)/libft.a $(LIB_DIR)

$(LIBMLX): $(LIB_DIR)
	$(MAKE) --directory=$(MLX_DIR)
	cp $(MLX_DIR)/libmlx.a $(LIB_DIR)

$(NAME): $(OBJ) $(LIBFT) $(LIBMLX)
	$(CC) $(LDFLAGS) $(OBJ) $(LDLIBS) -o $(NAME)

$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c | $(OBJ_DIR)
	$(CC) $(CPPFLAGS) $(CFLAGS) -c $< -o $@

$(OBJ_DIR) $(LIB_DIR):
	mkdir -p $@

clean:
	rm -rv $(OBJ_DIR)
	$(MAKE) clean --directory=$(LIBFT_DIR)
	$(MAKE) clean --directory=$(MLX_DIR)

fclean: clean
	rm $(NAME)
	$(MAKE) fclean --directory=$(LIBFT_DIR)

re: fclean all

-include $(OBJ:.o=.d)
```

##### libft
```Makefile
NAME	=	libft.a
RUNNER	=	runner

CC		=	gcc
CFLAGS	=	-Wall -Werror -Wextra

S		=	ft_atoi.c ft_bzero.c ft_calloc.c ft_isalnum.c ft_isalpha.c \
			ft_isascii.c ft_isdigit.c ft_isprint.c ft_itoa.c ft_memchr.c \
			ft_memcmp.c ft_memcpy.c ft_memmove.c ft_memset.c ft_putchar_fd.c \
			ft_putendl_fd.c ft_putnbr_fd.c ft_putstr_fd.c ft_split.c \
			ft_strchr.c ft_strdup.c ft_striteri.c ft_strjoin.c ft_strlcat.c \
			ft_strlcpy.c ft_strlen.c ft_strmapi.c ft_strncmp.c ft_strnstr.c \
			ft_strrchr.c ft_strtrim.c ft_substr.c ft_tolower.c ft_toupper.c \
# 			main.c
O		=	$(S:.c=.o)
BONUS_S	=	ft_lstnew_bonus.c ft_lstadd_front_bonus.c ft_lstsize_bonus.c \
			ft_lstlast_bonus.c ft_lstadd_back_bonus.c ft_lstdelone_bonus.c \
			ft_lstclear_bonus.c ft_lstiter_bonus.c ft_lstmap_bonus.c
BONUS_O	=	$(BONUS_S:.c=.o)
H		=	libft.h

RM		=	rm -rf

.PHONY:	all bonus clean fclean re

all bonus: $(NAME)

$(NAME): $(O) $(if $(findstring bonus, $(MAKECMDGOALS)), $(BONUS_O))
	ar rcs $(NAME) $(O) $(if $(findstring bonus, $(MAKECMDGOALS)), $(BONUS_O))

# needs to have 'int main()' to be functional
runner: $(O) $(BONUS_O)
	@$(CC) $(CFLAGS) -o $(RUNNER) $(O) $(BONUS_O)

%.o : %.c $(H)
	$(CC) $(CFLAGS) -c $< -o $(addsuffix .o, $(basename $<))

clean:
	$(RM) $(O) $(BONUS_O)

fclean: clean
	$(RM) $(NAME)

re: fclean all
```

##### Basic with wildcards
Beware that `*` works only for existing files, so don't use it in rules for object files. Use `%` pattern matching instead.

A basic and more or less universal example ([a version with tabs](https://pastebin.com/mXipJB9n), as Make has a very stupid relationship with spaces) (also a [gist](https://gist.github.com/demicuz/14f6a4e78776e12b82da4faccfd1473f)):
```Makefile
CC		=	gcc
CFLAGS	=	-Wall -Werror -Wextra

NAME	=	bsq

HDIR	=	./include/

S		=	$(wildcard *.c */*.c */*/*.c)
H		=	$(wildcard *.h */*.h */*/*.h)
O		=	$(S:.c=.o)

RM		=	rm -rf

.PHONY:	all clean fclean re

all:	$(NAME)

$(NAME):	$(O)
	@$(CC) $(CFLAGS) -o $(NAME) $(O)

.c.o:
	@$(CC) $(CFLAGS) -c $< -o $@ -I $(HDIR)

clean:
	@$(RM) $(O)

fclean:	clean
	@$(RM) $(NAME)

re:	fclean all
 ```

### jbelinda
![](https://i.imgur.com/xHqlmVK.png)
#todo

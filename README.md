# libft

> A custom C library reimplementing a subset of the standard C library, developed as a 42 School project.

---

## Table of Contents

- [Project Summary](#project-summary)
- [Skills Acquired](#skills-acquired)
- [Project Structure](#project-structure)
- [Build & Run](#build--run)
- [Usage](#usage)
- [Author](#author)

---

## Project Summary

**libft** is a foundational 42 School project in which the student builds a personal static C library (`libft.a`) from scratch. The library re-implements many of the most commonly used functions from `<string.h>`, `<ctype.h>`, `<stdlib.h>`, and `<unistd.h>`, as well as extra utility functions and a set of bonus linked-list functions. The resulting archive can be linked into any future 42 project, removing the dependency on the standard library where forbidden.

---

## Skills Acquired

- Deep understanding of how standard C library functions work internally.
- Memory management: manual allocation, zeroing, copying, and moving blocks of memory.
- String manipulation: length, copy, concatenation, search, split, trim, and join operations.
- Character classification and conversion (`isalpha`, `isdigit`, `toupper`, `tolower`, etc.).
- Writing and compiling a static library with `ar`.
- Working with file descriptors for low-level output (`write` syscall).
- Implementing singly-linked list operations (bonus): creation, traversal, insertion, deletion, mapping, and iteration.
- Makefile authoring: incremental builds, `clean`/`fclean`/`re` targets, and conditional bonus compilation.
- Strict compliance with the 42 Norm (code style rules).

---

## Project Structure

```
libft/
├── libft.h               # Public header — all function prototypes & t_list definition
├── Makefile              # Build rules
│
├── ft_is*.c              # Character classification functions
├── ft_to*.c              # Character conversion functions
├── ft_mem*.c             # Memory manipulation functions
├── ft_str*.c             # String manipulation functions
├── ft_put*_fd.c          # File-descriptor output functions
├── ft_atoi.c             # String-to-integer conversion
├── ft_itoa.c             # Integer-to-string conversion
├── ft_split.c            # String split by delimiter
├── ft_striteri.c         # String iteration with index
├── ft_strmapi.c          # String mapping with index
│
└── ft_lst*_bonus.c       # Bonus: singly-linked list functions
```

---

## Build & Run

All source files live in the `libft/` subdirectory. Run every `make` command from inside that directory.

```bash
cd libft
```

| Command        | Description                                              |
|----------------|----------------------------------------------------------|
| `make`         | Compile mandatory part → produces `libft.a`              |
| `make bonus`   | Compile mandatory + bonus (linked-list) functions        |
| `make clean`   | Remove object files (`.o`)                               |
| `make fclean`  | Remove object files **and** `libft.a`                    |
| `make re`      | Full recompile (`fclean` then `all`)                     |

**Example — build the library:**

```bash
cd libft
make
```

**Example — link against the library in your own project:**

```c
// main.c
#include "libft/libft.h"
#include <stdio.h>

int main(void)
{
    char *s = ft_strdup("Hello, libft!");
    printf("%s\n", s);
    free(s);
    return 0;
}
```

```bash
cc -Wall -Wextra -Werror main.c -Llibft -lft -o my_program
./my_program
```

---

## Usage

Once compiled, include `libft.h` in your source files and link with `libft.a`.

### Mandatory functions

| Category        | Functions |
|-----------------|-----------|
| Memory          | `ft_memset`, `ft_bzero`, `ft_memcpy`, `ft_memmove`, `ft_memchr`, `ft_memcmp`, `ft_calloc` |
| Strings         | `ft_strlen`, `ft_strchr`, `ft_strrchr`, `ft_strdup`, `ft_strlcpy`, `ft_strlcat`, `ft_strncmp`, `ft_strnstr`, `ft_substr`, `ft_strjoin`, `ft_strtrim`, `ft_split`, `ft_striteri`, `ft_strmapi` |
| Characters      | `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint`, `ft_toupper`, `ft_tolower` |
| Conversion      | `ft_atoi`, `ft_itoa` |
| Output (fd)     | `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd` |

### Bonus functions (linked list)

| Function            | Description                                         |
|---------------------|-----------------------------------------------------|
| `ft_lstnew`         | Create a new list node                              |
| `ft_lstadd_front`   | Add a node at the front of the list                 |
| `ft_lstadd_back`    | Add a node at the back of the list                  |
| `ft_lstlast`        | Return the last node                                |
| `ft_lstsize`        | Return the number of nodes                          |
| `ft_lstdelone`      | Delete a single node                                |
| `ft_lstclear`       | Delete all nodes in the list                        |
| `ft_lstiter`        | Apply a function to each node's content             |
| `ft_lstmap`         | Apply a function and return a new mapped list       |

---

## Author

| Name       | Login      | School       |
|------------|------------|--------------|
| ruortiz-   | ruortiz-   | 42           |

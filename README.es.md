# libft

> Una biblioteca C personalizada que reimplementa un subconjunto de la biblioteca estándar de C, desarrollada como proyecto de la escuela 42.

---

## Tabla de contenidos

- [Resumen del proyecto](#resumen-del-proyecto)
- [Habilidades adquiridas](#habilidades-adquiridas)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Compilación y ejecución](#compilación-y-ejecución)
- [Uso](#uso)
- [Autor](#autor)

---

## Resumen del proyecto

**libft** es el proyecto fundacional de la escuela 42 en el que el estudiante construye desde cero una biblioteca estática de C (`libft.a`). La biblioteca reimplementa muchas de las funciones más utilizadas de `<string.h>`, `<ctype.h>`, `<stdlib.h>` y `<unistd.h>`, así como funciones de utilidad adicionales y un conjunto de funciones bonus para listas enlazadas. El archivo resultante puede enlazarse en cualquier proyecto futuro de 42, eliminando la dependencia de la biblioteca estándar cuando ésta no está permitida.

---

## Habilidades adquiridas

- Comprensión profunda del funcionamiento interno de las funciones de la biblioteca estándar de C.
- Gestión de memoria: reserva manual, puesta a cero, copia y movimiento de bloques de memoria.
- Manipulación de cadenas: longitud, copia, concatenación, búsqueda, división, recorte y unión.
- Clasificación y conversión de caracteres (`isalpha`, `isdigit`, `toupper`, `tolower`, etc.).
- Escritura y compilación de una biblioteca estática con `ar`.
- Uso de descriptores de archivo para salida de bajo nivel (llamada al sistema `write`).
- Implementación de operaciones sobre listas enlazadas simples (bonus): creación, recorrido, inserción, eliminación, mapeo e iteración.
- Elaboración de Makefiles: compilación incremental, objetivos `clean`/`fclean`/`re` y compilación condicional del bonus.
- Cumplimiento estricto de la Norma 42 (reglas de estilo de código).

---

## Estructura del proyecto

```
libft/
├── libft.h               # Cabecera pública — todos los prototipos de funciones y definición de t_list
├── Makefile              # Reglas de compilación
│
├── ft_is*.c              # Funciones de clasificación de caracteres
├── ft_to*.c              # Funciones de conversión de caracteres
├── ft_mem*.c             # Funciones de manipulación de memoria
├── ft_str*.c             # Funciones de manipulación de cadenas
├── ft_put*_fd.c          # Funciones de salida por descriptor de archivo
├── ft_atoi.c             # Conversión de cadena a entero
├── ft_itoa.c             # Conversión de entero a cadena
├── ft_split.c            # División de cadena por delimitador
├── ft_striteri.c         # Iteración de cadena con índice
├── ft_strmapi.c          # Mapeo de cadena con índice
│
└── ft_lst*_bonus.c       # Bonus: funciones para listas enlazadas simples
```

---

## Compilación y ejecución

Todos los archivos fuente se encuentran en el subdirectorio `libft/`. Ejecuta todos los comandos `make` desde dentro de ese directorio.

```bash
cd libft
```

| Comando        | Descripción                                                   |
|----------------|---------------------------------------------------------------|
| `make`         | Compila la parte obligatoria → genera `libft.a`               |
| `make bonus`   | Compila las funciones obligatorias + bonus (listas enlazadas) |
| `make clean`   | Elimina los ficheros objeto (`.o`)                            |
| `make fclean`  | Elimina los ficheros objeto **y** `libft.a`                   |
| `make re`      | Recompilación completa (`fclean` seguido de `all`)            |

**Ejemplo — compilar la biblioteca:**

```bash
cd libft
make
```

**Ejemplo — enlazar la biblioteca en tu propio proyecto:**

```c
// main.c
#include "libft/libft.h"
#include <stdio.h>

int main(void)
{
    char *s = ft_strdup("Hola, libft!");
    printf("%s\n", s);
    free(s);
    return 0;
}
```

```bash
cc -Wall -Wextra -Werror main.c -Llibft -lft -o mi_programa
./mi_programa
```

---

## Uso

Una vez compilada, incluye `libft.h` en tus archivos fuente y enlaza con `libft.a`.

### Funciones obligatorias

| Categoría       | Funciones |
|-----------------|-----------|
| Memoria         | `ft_memset`, `ft_bzero`, `ft_memcpy`, `ft_memmove`, `ft_memchr`, `ft_memcmp`, `ft_calloc` |
| Cadenas         | `ft_strlen`, `ft_strchr`, `ft_strrchr`, `ft_strdup`, `ft_strlcpy`, `ft_strlcat`, `ft_strncmp`, `ft_strnstr`, `ft_substr`, `ft_strjoin`, `ft_strtrim`, `ft_split`, `ft_striteri`, `ft_strmapi` |
| Caracteres      | `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint`, `ft_toupper`, `ft_tolower` |
| Conversión      | `ft_atoi`, `ft_itoa` |
| Salida (fd)     | `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd` |

### Funciones bonus (lista enlazada)

| Función             | Descripción                                              |
|---------------------|----------------------------------------------------------|
| `ft_lstnew`         | Crear un nuevo nodo de lista                             |
| `ft_lstadd_front`   | Agregar un nodo al frente de la lista                    |
| `ft_lstadd_back`    | Agregar un nodo al final de la lista                     |
| `ft_lstlast`        | Devolver el último nodo                                  |
| `ft_lstsize`        | Devolver el número de nodos                              |
| `ft_lstdelone`      | Eliminar un único nodo                                   |
| `ft_lstclear`       | Eliminar todos los nodos de la lista                     |
| `ft_lstiter`        | Aplicar una función al contenido de cada nodo            |
| `ft_lstmap`         | Aplicar una función y devolver una nueva lista mapeada   |

---

## Autor

| Nombre     | Login      | Escuela      |
|------------|------------|--------------|
| ruortiz-   | ruortiz-   | 42           |

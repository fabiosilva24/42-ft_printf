# ft_printf

A custom implementation of the C `printf` function that formats and prints data to the standard output.

## Description

This project recreates the behavior of the standard C library `printf` function. It handles various format specifiers and provides formatted output functionality.

## Supported Format Specifiers

- `%c` - Single character
- `%s` - String of characters
- `%p` - Pointer address in hexadecimal format
- `%d` / `%i` - Signed decimal integer
- `%u` - Unsigned decimal integer
- `%x` - Unsigned hexadecimal integer (lowercase)
- `%X` - Unsigned hexadecimal integer (uppercase)
- `%%` - Literal percent sign


## Building the Library

To compile the library:

```bash
make
```

This will create a `libftprintf.a` library file.

## Usage

Include the header file in your C program:

```c
#include "ft_printf.h"
```

Link the library when compiling:

```bash
cc your_program.c -L. -lftprintf
```

## Example Usage

```c
#include "ft_printf.h"

int main(void)
{
    ft_printf("Hello %s!\n", "World");
    ft_printf("Number: %d\n", 42);
    ft_printf("Hex: %x\n", 255);
    ft_printf("Pointer: %p\n", &main);
    return (0);
}
```

## Function Prototype

```c
int ft_printf(const char *format, ...);
```

Returns the number of characters printed (excluding the null terminator).

## Features

- Handles NULL string pointers by printing "(null)"
- Handles NULL pointers by printing "(nil)"
- Proper handling of edge cases like `INT_MIN`
- Memory-safe implementation
- Flag support for enhanced formatting

## Make Commands

- `make` - Compile the library
- `make clean` - Remove object files
- `make fclean` - Remove object files and library
- `make re` - Rebuild everything

## Requirements

- C compiler (cc/gcc/clang)
- Standard C library headers
- Unix-like system (for `write` system call)

In C++, character literals are chars, therefore the size 1

```c++
// recall that sizeof is a unary operator that retuns the size of a data type in bytes.
// recall that 1 byte == 8 bits
sizeof('c'); // -> 1
sizeof('c') == sizeof(char); // -> true
```

In C, char literals are ints, therefore the size is 4

```c
sizeof('c'); // -> 4 bytes.
sizeof('c') == sizeof(int); // -> true
```

C++ has strict prototyping.

```c++
void func();     // function which accepts no arguments
void func(void); // same as earlier

// in C
void func();     // function which may accept any number of arguments with unkown type
void func(void); // function which accepts no arguments
```

Because of that, the following code will throw a compilation error in C++ but not in C (even with
-Wall and -Wextra)

```c++
int func()
{
    return 5;
}

int main()
{
    int result = func(1, 2);
    printf("%d\n", result);
    return 0;
}
```

Use nullptr instead of NULL in C++

```c++
int *ip = nullptr;
```

Note that in C, Null pointers are special pointer values that do not point to any valid memory location.
Pointers can be initialized to NULL to indicate that they do not currently point to any object or data.
This prevents them from being "wild pointers" that could point to arbitrary, potentially invalid, memory addresses.

```c
int *ip = NULL;
```

Most C standard heades are available in C++;
C headers generally end with a .h, while C++ headers are prefixed with "c" and have no ".h" suffix.

The C++ standard version:

```c++
#include <cstdio>
```

The C standard version:

```c
#include <stdio.h>
```

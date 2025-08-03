# Default function arguments

You can set default arguments for a function (like in JavaScript).
Which will be then evaluated in case the caller do not provide it.
Example:

```c++
void foo(int a = 1, int b = 2)
{
    // do something...
}

int main()
{
    foo();      // a = 1,  b = 4
    foo(20);    // a = 20, b = 4
    foo(20, 5); // a = 20, b = 5
}
```

Once you set a default arg for a single parameter, you got to set for all of them.

```c++
void invalidDeclaration(int a = 1, int b) // Error!
{
}
```

I think in C, this is not a thing since we can just use a shortcircuit within the function itself
to set default values.

```c
// THIS WOULD NOT COMPILE!
// We would have a "too few arguments error"
void foo(int a, int b)
{
    // set default values
    a = a || 1;
    b = b || 4;
    printf("a is: %d | b is %d\n", a, b);
}

int main(int argc, char *argv[])
{
    foo();
    foo(20);
    foo(20, 5);
    return 0;
}
```

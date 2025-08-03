# Function Overloading

C++ supports function overloading, provided each function takes different parameters.

Function overloading in programming refers to the ability to define multiple function within
the same scope that share name but differ in their parameter list.
Example:

```c++
void print(const char* myString)
{
    printf("String: %s\n", myString);
}

void print(int myInt)
{
    printf("My int is: %d\n", myInt);
}

int main()
{
    print("Hello");
    print(15);
}
```

That's why the following code compiles succesfully in C++ but not in C.

```c++
void foo(const char* string)
{
    printf("My string: %s\n", string);
}

void foo(int myNum)
{
    printf("My integer: %d\n", myNum);
}

int main(int argc, char *argv[])
{
    foo("TposeProgrammer");
    foo(3);
    return 0;
}
```

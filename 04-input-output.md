# Input / Output

C++ input and output uses streams.
cin, cout and cerr represent stdin, stdout, and stderr.
or character in, character out and character error respectively.
<< is the insertion operator and >> is the extraction operator.

```c++
#include <iostream> // Include for I/O streams

int main()
{
    int myInt;

    // Prints to stdout (or terminal/screen)
    // std::cout referring the access to the std namespace
    std::cout << "Enter your favorite number:\n";
    // Takes in input
    std::cin >> myInt;

    // cout can also be formatted
    std::cout << "Your favorite number is " << myInt << '\n';
    // prints "Your favorite number is <myInt>"

    std::cerr << "Used for error messages";

    // flush string stream buffer with new line
    std::cout << "I flushed it away" << std::endl;
}
```

Note that: std::cout = "standard character output". (like `stdout` in C)
`<<` = _insertion operator_. It inserts data into the output stream (to the screen).
Example

```c++
std::out << "Hello";

// same as
printf("Hello");
```

You can chain insertions:

```c++
std::out << "A " << 42 "\n";
```

Note that: std::cin = "standard character input" (like `stdin` in C)
`>>` = _extraction operator_. It extracts data from the input stream (the keyboard).
Example:

```c++
int myInt;
std::cin >> myInt;
```

Same as:

```C
int myInt;
scanf("%d\n", myInt);
```

Note that std::cerr = "Standard character error" (like `stderr` in C).
Good for printing error messages.

# Namespaces

Namespaces provide separate scopes for variable, function, and other declarations.
Namespaces can be nested.

```c++
namespace First {
    namespace Nested {
        void foo()
        {
            printf("This is First::Nested::foo\n");
        }
    } // end namespace Nested
} // end namespace First

namespace Second {
    void foo() {
        printf("This is Second::foo\n");
    }

    void bar() {
        printf("This is Second::bar\n");
    }
}

void foo()
{
    printf("This is global foo\n");
}

int main()
{
    // Includes all symbols from namespace Second into the current scope. Note that
    // while bar() works, simply using foo() no longer works, since its now ambiguous
    // wheter we're calling the foo in namespace Second or the top level.
    using namespace Second;

    bar();                // prints: This is Second::bar
    Second::foo();        // prints: This is Second::foo
    First::Nested::foo(); // prints: This is First::Nested::foo
    ::foo();              // prints: This is global foo
}
```

`::` is known as the _scope resolution operator_. it specifies the scope to which and indentifier
(like a variable, function or class) belongs.

Some examples of use case:

- Accessing Global Variables with Local Variables of the Same Name:

```c++
int global_var = 10;

int main()
{
    int global_var = 20; // local variable
    std::cout << "Local: " << global_var << std::endl;  // Prints 20
    std::cout << "Global: " << ::global_var << std::endl; // Prints 10
    return 0;
}
```

- Defining Member Functions Outside a Class:

```c++
class MyClass {
public: // Access specifier: members declared here are accessible from outside the class
    void printMessage();
};

void MyClass::printMessage() { // Defining printMessage outside the class
    std::cout << "Hello from MyClass!" << std::endl;
}
```

- Accessing Members of a Namespace:

```c++
namespace MyNamespace
{
    void greet() {
        std::cout << "Greetings from MyNamespace!" << std::endl;
    }
}

int main()
{
    MyNamespace::greet(); // Calls the greet function in MyNamespace
    return 0;
}

// alternatively we could do the following:

int main()
{
    using namespace MyNamespace;
    greet(); // This only works because there is no other function called greet in the global scope.
    return 0;
}

```

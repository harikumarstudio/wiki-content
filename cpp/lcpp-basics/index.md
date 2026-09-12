---
title: "C++ Basics"
description: "How basic C++ programs are constructed"
authors:
  - harikumarstudio
related:
tags:
  - article 
---


## 1.1 - Statements and the structure of a program 

- __Statements__ = are a type of instruction that causes some action 
- `;` = semi colons are placed at the end of a statement 
- __Functions__ = are a collection of statements read from top to bottom 
- `main()` = is a function that every program must have
- `doSomething()` = end brackets are shorthand for a function named doSomething

### Dissecting Hello, World!

```cpp
#include <iostream>

int main()
{
	std::cout << "Hello world!"; 
	return 0;
}

```

1. Line 1 includes the `#include` preprocessor directive which indicates use of the _iostream_ content library, which is part of the C++ standard library. It is needed in order to use the `cout` on line 5. 
2. Line 2 is blank and ignored by the compiler. A space makes it easier to read for humans.
3. Line 3 defines the functin with the name `main` and whose value type is `int` (integer). 
4. Lines 4 and 7 tell which lines are part of the main function or the function body. 
5. Line 5 is the first statement within main, it displays the text `"Hello World"` to the console as output (cout). 
6. Line 6 is the return statement which returns 0 if the program ran successfully. 


## 1.2 - Comments

```cpp
#include <iostream> // Short single line comment (Aligned to right)

// Aligned above for longer comments 
int main()
{
	std::cout << "Hello world!"; 
	return 0;
}

/* 
Multi 
line
comments, 
using pair of symbols 
*/ 

```

<aside>
When commenting out code, use either depending on case.
</aside>

**Visual Studio shortcuts:** 
- <kbd>Ctrl + /</kbd> for single line
- <kbd>Ctrl + Shift + /</kbd> for multi-line 


## 1.3 - Introduction to objects and variables


- **Data** - information that can be moved, processed or stored by the computer 
- **Code** - Program itself 
- **Value** - Single piece of data
  - Numbers (1, -3.5)
  - Characters, placed between single quotes('H' or '$')
  - Text, which must be placed between double-quotes("Hello" or "H")
- Values places directly into code = _literals_ 
- Random Access Memory (RAM) series of numbered boxes that stores or loads values to be used later on
- Direct memory access is discouraged, instead, an object represents a region of storage
- An object with a name is a _variable_

```cpp
// define a variable named "x" of type "int" 
int x; 

```

- Data types must be known at compile time
- Custom types are also a possibility 

```cpp
// multiple variables should be listed in a separate statement on its own lin  
int a; 
double b; 

```

## 1.4 - Variable assignment and initialization 

- After a variable has been defined, give it a value using `=`

```cpp 
int width; 
width = 5; //copy assignment 
width = 10; // overwrite previous value by assigning a new value later

```

- `=` - Assignment
- `==` - Equality test 

### Variable initialization

- Specifying own initial value for an object is called initialization

```cpp 
int width = 5;    // traditional initialization 
int width { 5 };  // modern initialization 

```

- Curly braces `{}` - is list-initializing (preferred method)
- List-initialization disallows narrowing conversions 

```cpp 
int w1 {4.5}; // error 
int w2 = 4.5; // converted to 4
int w3 (4.5); // converted to 4

```

- `int width{};` - zero-initialization 
- If using value of 0 right away, then specify 0
- If not, and the value is being replaced, do not explicitly state 0 
- Unused variable warnings, will happen if a variable had been defined but not used in the program 
- `[[maybe_unused]]` attribute can be used to skip the warnings (C++17)
- Always initialize your variables (cost is minscule compared to benefit)


## 1.7 - Keywords and naming identifiers 


- **92** Keywords reserved (As of C++23) 

 <details>
    <summary>For the full list, please see below</summary>

    alignas
    alignof
    and
    and_eq
    asm
    auto
    bitand
    bitor
    bool
    break
    case
    catch
    char
    char8_t (since C++20)
    char16_t
    char32_t
    class
    compl
    concept (since C++20)
    const
    consteval (since C++20)
    constexpr
    constinit (since C++20)
    const_cast
    continue
    co_await (since C++20)
    co_return (since C++20)
    co_yield (since C++20)
    decltype
    default
    delete
    do
    double
    dynamic_cast
    else
    enum
    explicit
    export
    extern
    false
    float
    for
    friend
    goto
    if
    inline
    int
    long
    mutable
    namespace
    new
    noexcept
    not
    not_eq
    nullptr
    operator
    or
    or_eq
    private
    protected
    public
    register
    reinterpret_cast
    requires (since C++20)
    return
    short
    signed
    sizeof
    static
    static_assert
    static_cast
    struct
    switch
    template
    this
    thread_local
    throw
    true
    try
    typedef
    typeid
    typename
    union
    unsigned
    using
    virtual
    void
    volatile
    wchar_t
    while
    xor
    xor_eq
  </details>

- Automatically converted to blue text in Visual Studio

### Identifier naming rules 

1. No Keywords 
2. No symbols (except underscore (_))
3. No numbers at start 
4. Case sensitive (nvalue, nValue, NVALUE)
  - Single word - all lowercase 
  - Two words - start with lowercase
    - Separated by underscore/snake_case = function_name
    - Separated by camelCase = functionName (preferred)
5. Name/identify functions as appropriate 
  - Specific enough to need a longer or shorter name 
  - Descriptive enough to undertand what it does / improve readability


## 1.8 - Whitespace and basic formatting 

- Use whitespace to format dense code like in the example below: 

```cpp
#include <iostream>
int main() {
std::cout << "Hello world";
return 0;
}

```
The following is a better way of formatting

```cpp
#include <iostream>             // preprocessor directives separate lines
#include <string>

int main()                      // whitespace between int and main
{
	std::cout << "Hello world!";  // Spaces between quoted text is taken  literally
	return 0;
}

```

Comments aligned to the right or above code, with spacing, make it easier to read: 

```cpp
// cout lives in the iostream library
std::cout << "First line of code!\n";

// these comments are easier to read
std::cout << "Second line of code!\n";

// when separated by whitespace
std::cout << "Third line of code!\n";

```

**Visual Studio shortcut** - <kbd>Ctrl + K</kbd> and <kbd>Ctrl + F</kbd> 

- [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines#main) maintained by Bjarne Stroustrup and Herb Sutter is a style guide on programming conventions, formatting guidelines and best practices. 


## 1.9 - Introduction to literals and operators

- **Literals** (also known as constants) - have a fixed value that has been inserted dirctly into the source code 
- **Variable** - its value can be changed
- **Operation** - the process of having input values producing a new value 
- **Return Value** - output value
- **Operator** - symbol of operation: `+, -, *, /, =, <<, >>, ==
- It is common to append an operator symbol to the word _operator_, eg. `operator+` or `operator>>`
- **Arity** - is the number of operands that the operator takes as input
  - _Unary_ (-5) - operator- takes literal operand 5 and flips its sign to produce a new output 
  - _Binary_ (3+5) - operator+ takes two operands: 3 and 5

## 1.10 - Introduction to expressions

- The result of an expression is most commonly a value 
- `type identifier { expression };` - `type` could be any valid type, `identifier` could be any valid name. `expression` could be any valid expression, using _literals_, _variables_ and _operators_. 

## 1.11 - Developing your first program

- First and primary goal of programming is to make the program work.
- However, the best solution often isn't obvious - optimize for maintainability. 
- Programming is an iterative process, one requiring repeated passes. 

Here are a few solutions for a simple program that converts a measurement in inches to centimetres.

The following is pseudocode for what we want it to do: 

1. `x = input length in inches`
2. `y = multiply x by 2.54`
3. `The length in centimetres is y`

**The not-good solution**

```cpp
#include <iostream>

// worst version
int main()
{
	std::cout << "Enter length in inches: ";

	double length{ };
	std::cin >> length;

	length = length * 2.54; // multiply length value by 2.54, then assign that value back to length

	std::cout << "The length in centimetres is: " << length << '\n';

	return 0;
}

```

Why this is a bad solution: 
  1. The `length` variable contains the users input. After being multiplied, it contains a different value. That's confusing.
  2. The `length` has been overwritten and now cannot be recalled if the program needed the initial value again.

**The mostly-good solution**

```cpp
#include <iostream>

// less-bad version
int main()
{
	std::cout << "Enter length in inches: ";

	double length{ };
	std::cin >> length;

  double cmlength{ length * 2.54 } // define a new variable and initialize it with length * 2.54
	std::cout << "The length in centimetres is: " << cmlength << '\n'; // then print the value of that variable here 

	return 0;
}

```

Why this is a bad solution: 
  1. Primary downside here is that we're defining a new variable (which adds complexity) to store a value we only use once. 

**The preferred solution**

```cpp
#include <iostream>

// preferred version
int main()
{
	std::cout << "Enter length in inches: ";

	double length{ };
	std::cin >> length;

	std::cout << "The length in centimetres is: " << length * 2.54 << '\n'; // use an expression to multiply length * 2.54 at the point we are printing it 

	return 0;
}

```

This is the preferred solution because the only variable `length` does not change and can be used later if needed. The requested result in cm is evaluated right when it is needed with the expression `length * 2.54`. 

# Modern C++ Notes
Notes to study modern C++ with the book C++ Prime (thank you Manuel).

Shortcuts:
<ul>
    <li><a href="#variables-and-basic-types">Variables and Basic types</a></li>
        <ul>
            <li><a href="#primitive-built-in-types">Primitive Built-In Types</a></li>
            <ul>
                <li><a href="#arithmetic-types">Arithmetic Types</a></li>
                <li><a href="#signed-and-unsigned-types">Signed and Unsigned Types</a></li>
            </ul>
        </ul>
    <li><a href="#string-vectors-and-arrays">String, Vectors and Arrays</a></li>
    <li><a href="#expressions">Expressions</a></li>
<ul>

## Variables and Basic Types
C++ has a extensive support for types. The language defines several primitive types and provides mechanisms that let us define our own data types. The library uses these mechanisms to define more compliucated types such as variable-length character strings, vectors, and so on.

<a href="#modern-c-notes">Back to top</a>

### Primitive Built-In Types
C++ defines a set of primitive types that include the arithmetic types and a special type named void. The arithmetic types represent characters, integers, boolean values, and floating=point numbers. The void types has no associated values and can be used in only few circumstances, most commonly as the return type for fubnctions that do not return a value.

<a href="#modern-c-notes">Back to top</a>

#### Arithmetic Types
The arithmetic types are divided into two categories: integral types (which include character and boolean types) and floating-point types.

The size of-that is, the number of bits in-the arithmetic tyoes varies across machines. The standard guarantees minimum sizes, however, compilers are allowed to use larger sizes for these tyoes, Because the number of bits varies, the largest (or smallest) value that a type can represent also varies.

There are several character types, most of which exist to support internationalization. The basic character types is `char`. A char is guaranteed to be big enough to hold numeric values corresponding to the characters in the machine's basic character set. That is, a `char` is the same size as a single machine byte.

The remaining character types - `wchar_t`, `char16_t`, and `char32_t` - are used for extended character sets. The `wchar_t` type is guaranteed to be large enough to hold any character in the machine's largest extended character set. The types `char16_t` and `char32_t` are intended for Unicode characters. (Unicode is a standard for representing characters used in essentially any natural language.)

The remaining integral types represent integer values of (potentially) different sizes. The language guarantees that an `int` will be at least as large as `short`, a `long` at least as large as an `int`, and `long long` at least as large as `long`. The type `long long` was introduced by the new standard (C++ 11).

<a href="#modern-c-notes">Back to top</a>

#### Signed and Unsigned Types
Except for `bool` and the extended character types, the integral types may be **signed** or **unsigned**. A signed type represents negative or positive numbers (including zero); an unsigned type represents only values greater than or equal to zero.

The types `int`, `short`, `long`, and `long long` are all signed. We obtain the corresponding unsigned type by adding `unsigned` to the type, such as `unsigned long`. The type `unsigned int` may be abbreviated as `unsigned`.

Unlike the other integer types, there are three distinct basic character types: `char`, `signed char`, and `unsigned char`. In particular, `char` is not the same type as `signed char`. Although there are three character types, there are only two representations: signed and unsigned. The (plain) `char` type uses one of these representations. Which of the other two character representations is equivalent to `char` depends on the compiler.

In an unsigned type, all the bits represent the value. For example, an 8-bit `unsigned char` can hold the values from 0 through 255 inclusive.

The standard does not define how signed types are represented, but does specify that the range should be evenly divided between positive and negative values. Hence, an 8-bit `signed char` is guaranteed to be able to hold values from -127 through 127; most modern machines use representations that allows values from -128 through 127.

<a href="#modern-c-notes">Back to top</a>

## String, Vectors and Arrays
In addition to the built-in types, C++ defines a rich library of abstract data types. Among the most important library types are `string`, which supports variable-length characters strings, and `vector`, which defines variable-size collections. Associated with `string` and `vector` are companion types known as iterators, which are used to access the characters in a `string` or the elements in a `vector`.

The `string` and `vector` types defined by the library are abstractions of the more primitive built-in array type. This chapter covers arrays and introduces the library `vector` and `string` types.

<a href="#modern-c-notes">Back to top</a>

### Library `string` Type
A `string` is a variable-length sequence of characters. To use the `string` type, we must include the `string` header. Because it is part of the library, `string` is defined in the `std` namespace. Our examples assume the following code:
```cpp
#include <string>
using std::string
```

#### Defining and Initializing `string`s
Each class defines how objects of its type can be initialized. A class may define many different ways to initialize objects of its type. Each way must be distinguished from the others either by the numberof initializers that we supply, or by the types of those initializers.

Ways to initialize a string:
```cpp
string s1;              // Default initialization; s1 is the empty string
string s2(s1);          // s2 is a copy of s1.
string s2 = s1;         // Equivalent to s2(s1), s2 is a copy of s1.
string s3("value");     // s3 is a copy of the string literal, not including the null.
string s3 = "value";    // Equivalent to s3("value"), s3 is a copy of string literal.
string s4(n, 'c');      // Initialize s4 with n copies of the character 'c'.
```

We can default initialize a `string`, which creates an empty string; that is, a string with no characters. When we supply a string literal, the characters from that literal--up to but not including the null character at the end of the literal--are copied into the newly created string. When we supply a count and a character, the string contains that many copies of the given character.

<a href="#modern-c-notes">Back to top</a>

## Expressions

<a href="#modern-c-notes">Back to top</a>
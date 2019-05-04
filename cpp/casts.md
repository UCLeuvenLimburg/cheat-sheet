---
layout: default
---
# Casts

```cpp
// Working example
class Shape                     { ... };
class Circle  : public Shape    { ... };
class Square  : public Shape    { ... };

class Vehicle                   { ... };
class Car     : public Vehicle  { ... };
```

## static_cast

[`static_cast`](https://en.cppreference.com/w/cpp/language/static_cast) performs only compile-time checks.

```c++
Shape* shape = new Circle();

Circle* circle = static_cast<Circle*>(shape); // ok
circle->method(); // ok

Square* square = static_cast<Square*>(shape); // compiles
square->method(); // undefined behavior!

Car* car = static_cast<Car*>(shape); // compile error
```

## dynamic_cast

[`dynamic_cast`](https://en.cppreference.com/w/cpp/language/dynamic_cast) performs both compile-time and run-time checks.
If the cast is invalid, the resulting pointer is `nullptr`. When using `dynamic_cast`, *always* check
the result, otherwise you might as well use `static_cast`.

```c++
Shape* shape = new Circle();

Circle* circle = dynamic_cast<Circle*>(shape); // ok
circle->method(); // ok

Square* square = dynamic_cast<Square*>(shape); // compiles
// square == nullptr

Car* car = dynamic_cast<Car*>(shape); // compile error
```

## reinterpret_cast

[`reinterpret_cast`](https://en.cppreference.com/w/cpp/language/reinterpret_cast) is the most dangerous cast
and allows you to change types at will. It tells the compiler to change its interpretation of the same bits.

```c++
float f;
int n = *reinterpret_cast<int*>(&f);
```

## const_cast
[`const_cast`](https://en.cppreference.com/w/cpp/language/const_cast) can be used
to remove `const`. You should never use this cast: needing it indicates
that your design is flawed. Also, it is never a good solution, since
modifying a formerly `const` value leads to undefined behavior.

```cpp
const int x = 5;
const T* p = &x;
T* q = const_cast<T*>(p);
++*q; // undefined behavior!
```

The reason for its existence is to allow to interact with ill-designed
libraries, e.g. call functions that do not change their
arguments yet do not declare them `const`.

## C-style Cast

The [C-style cast](https://en.cppreference.com/w/cpp/language/explicit_cast) tries out combinations of the above casts.
To be avoided.
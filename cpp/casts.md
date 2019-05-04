---
layout: default
---
# Casts

```cpp
// Working example
class Shape { ... };
class Circle : public Shape { ... };
class Square : public Shape { ... };

class Vehicle { ... };
class Car : public Vehicle  { ... };
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
---
layout: default
---
# Pointers and References

## Pointers T*

|Syntax|Meaning|
|:-:|-|
| `T*` | Pointer to `T` |
| `&x` | Address of `x` |
| `*x` | Dereference `x` |

The `&` and `*` are each others complement: `*` undoes `&`.

```cpp
int x = 5;
int* p = &x; // Create pointer to x
int y = *p;  // Dereference y
```

## References T&

```cpp
int x = 5;
int& y = x; // y is an alias for x. x and y are indistinguisable
```

## std::unique_ptr

[`std::unique_ptr<T>`](https://en.cppreference.com/w/cpp/memory/unique_ptr)
creates a pointer that *owns* its pointee: this means that whenever
a unique pointer goes out of scope, it deletes the pointee.

Create a unique pointer using `std::make_unique<T>(args)`, where
`args` are arguments that are accepted by one of `T`'s constructors.

```cpp
#include <memory>

struct Person
{
    Person(const std::string& name, int age);
};

std::unique_ptr<Person> p = std::make_unique<Person>(name, age);
```

At all times, an object can only be pointed to by one unique pointer.
For this reason, you cannot simply call a function with a unique pointer:
it would be copied and there would be two unique pointers fighting for ownership.
Instead, a unique pointer must be *moved*:

```cpp
void func(std::unique_ptr<T> p);

std::unique_ptr<T> my_ptr;
func(std::move(my_ptr)); // force a move instead of copy
// my_ptr is now nullptr
```

## std::shared_ptr

Shared pointers share ownership over a pointee: when the last shared pointer
goes out of scope, it frees the pointee.

```cpp
#include <memory>

struct Person
{
    Person(const std::string& name, int age);
};

std::shared_ptr<Person> p = std::make_shared<Person>(name, age);
```

## Guidelines

When trying to determine the type for a parameter,
ask yourself the following questions:

* How large is it value that needs to be passed?
* Does the function require write access?
* Does the function keep the data around or does it throw it away after it's done?

An example of the third kind of function is a constructor
that will store the given data in a field.

|Size|Write|Store|Type|
|:-:|:-:|:-:|:-:|
|Small|No|No| `T` |
|Large|No|No| `const T&` |
| |Yes|No| `T*` |
| |No|Yes| `std::shared_ptr<const T>` |
| |Yes|Yes| `std::shared_ptr<T>` |

A `std::unique_ptr<T>` is generally used for objects
that have exclusive access to the pointee.

```cpp
template<typename T>
class container
{
    std::unique_ptr<T> data;

public:
    container()
      : data(std::make_unique<T[]>(initial_capacity)) { }
};
```
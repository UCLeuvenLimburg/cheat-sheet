---
layout: default
---
# Inheritance

## Public Inheritance

```cpp
class Super { };
class Sub : public Super { };
```

| Members in base class | Members in subclass |
|:-:|:-:|
| `public` | `public` |
| `protected` | `protected` |
| `private` | `private` |

Subtyping: a `Sub*` can be cast to `Super*` and vice versa.

## Protected Inheritance

```cpp
class Super { };
class Sub : protected Super { };
```

| Members in base class | Members in subclass |
|:-:|:-:|
| `public` | `protected` |
| `protected` | `protected` |
| `private` | `private` |

Subtyping: a `Sub*` can be cast to `Super*` and vice versa, only within the hierarchy.

## Private Inheritance

```cpp
class Super { };
class Sub : Super { };
```

| Members in base class | Members in subclass |
|:-:|:-:|
| `public` | `private` |
| `protected` | `private` |
| `private` | `private` |

Subtyping: a `Sub*` can only be cast to `Super*` and vice versa inside `Sub`.
To the outside world, `Super` and `Sub` appear unrelated.

## Virtual

```cpp
class Shape
{
public:
    virtual ~Shape() { }    // Virtual destructor
    virtual void foo();     // Overridable, must have body defined somewhere
    virtual void bar() = 0; // Abstract method
};
```

While not strictly necessary anymore thanks to smart pointers, it might be safer to
still define a virtual destructor in a class hierarchy's superclass,
empty if need be.

## Interfaces

An interface in C++ is nothing more than a class
with nothing but pure virtual member functions.

```cpp
class InterfaceName
{
public:
    virtual void foo() = 0;
    virtual void bar() = 0;
};
```

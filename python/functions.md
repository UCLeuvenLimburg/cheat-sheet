---
layout: default
---
# Functions

## Definition

```python
def greet(who):
    print(f"Hello, {who}")

greet("John")
# prints Hello John

foo(who="Peter")
# prints Hello Peter
```

## Default Parameter Values

```python
def foo(x = 5):
    return x ** 2

foo(2)
# => 4

foo()
# => 25
```

## Variadic Functions

```python
def foo(*args, **kwargs):
    # args is a list
    # kwargs is a dictionary
    return (args, kwargs)

foo()
((), {})

foo(1, 2)
((1, 2), {})

foo(x=1, y=2)
((), {'x': 1, 'y': 2})

foo(1, 2, x=3, y=4)
((1, 2), {'x': 3, 'y': 4})
```
---
layout: default
---
# Typing

[Official documentation](https://docs.python.org/3/library/typing.html)

## Types

```python
Any
str
int
float
Sequence[T]
MutableSequence[T]
List[T]
Tuple[T1, T2, ...]
AbstractSet[T]
MutableSet[T]
Mapping[K, V]
MutableMapping[K, V]
Callable[[P1, P2, ...], R]
```

## NewType

```python
from typing import NewType

Age = NewType('Age', int)
```

## Generics

```python
from typing import TypeVar, Generic


T = TypeVar('T')

class SomeClass(Generic[T]):
    ...
```
---
layout: default
---
# Lists

[Official Documentation](https://docs.python.org/3/tutorial/datastructures.html#sets)

* Sets do not preserve order
* Sets cannot contain multiple instances of the same element
* Checking if an element occurs in the set is very efficient

## Creation

```python
# Literal
s = set()          # Empty set
s = { }            # Empty dictionary!!
s = { 1, 2, 3, 4 }
```

## Set Comprehension

```python
s = { x**2 for x in range(1, 5) }
# => { 1, 4, 9, 16 }
```

## Operations

| Syntax | Semantics |
|-|-|
| `x in s` | Check if `x` occurs in `s` |
| `s1 | s2` | Union |
| `s1 - s2` | Difference |
| `s1 & s2` | Intersection |
| `s.add(x)` | Add `x` to `s` |
| `s1 < s2` | Check if `s1` a strict subset of `s2` |
| `s1 <= s2` | Check if `s1` a subset of `s2` |
| `s1 > s2` | Check if `s1` a strict superset of `s2` |
| `s1 >= s2` | Check if `s1` a superset of `s2` |
| `s.pop()` | Removes and returns a random element from `s` |

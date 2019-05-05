---
layout: default
---
# Lists

## Literal

```python
xs = [ 1, 2, 3, 4, 5 ]
```

## Operations

| Syntax | Semantics |
|-|-|
| `xs[i]` | Reading value at index `i` |
| `xs[i] = y` | Overwriting value at index `i` |
| `len(xs)` | Length of `xs` |
| `xs[i:j]` | Copy slice from `i` to `j` (exclusive) |
| `xs[i:]` | Copy slice from `i` to end |
| `xs[:j]` | Copy slice until `i` (exclusive) |
| `xs.append(y)` | Add `y` at the end of `xs` |
| `xs.insert(i, y)` | Insert `y` at index `i` |
| `xs.extends(ys)` | Add all elements of `ys` at end of `xs` |
| `del(xs[i])` | Remove item with index `i` |
| `xs.remove(y)` | Remove first occurrence of `y` |
| `xs.clear()` | Empty list |
| `xs.count(y)` | Count number of occurrences of `y` |
| `xs.reverse()` | Reverses list in place |
| `reversed(xs)` | Reverses list as new sequence |
| `xs.sort()` | Sorts in place |
| `xs.sort(key=func)` | Sorts in place using `func` to determine order |

## List Comprehensions

```python
# Collect the names of persons
xs = [ person.age for person in people ]

# Collect the names of men
xs = [ person.age for person in people if person.male ]
```

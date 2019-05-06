---
layout: default
---
# Lists

[Official Documentation](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)

## Creation

```python
# Literal
xs = [ 1, 2, 3, 4, 5 ]
```

## List comphrension

```python
# Collect the names of persons
xs = [ person.age for person in people ]

# Collect the names of men
xs = [ person.age for person in people if person.male ]

# Nested loops
xs = [ (x, y) for x in range(1, 3) for y in range(1, 3) ]
# => [(1, 1), (1, 2), (2, 1), (2, 2)]
```

## Operations

| Syntax | Semantics |
|-|-|
| `xs[i]` | Read value at index `i` |
| `xs[i] = y` | Overwrite value at index `i` |
| `len(xs)` | Length of `xs` |
| `xs[i:j]` | Copy slice from `i` to `j` (exclusive) |
| `xs[i:]` | Copy slice from `i` to end |
| `xs[:j]` | Copy slice until `i` (exclusive) |
| `xs.append(y)` | Add `y` at the end of `xs` |
| `xs.insert(i, y)` | Insert `y` at index `i` |
| `xs + ys` | List concatenation |
| `xs * n` | List with `n` repetitions of `xs` |
| `y in xs` | Checks if `y` occurs in `xs` |
| `del(xs[i])` | Remove item with index `i` |
| `xs.remove(y)` | Remove first occurrence of `y` |
| `xs.clear()` | Empty list |
| `xs.count(y)` | Count number of occurrences of `y` |
| `xs.reverse()` | Reverses list in place |
| `reversed(xs)` | Reverses list as new sequence |
| `xs.sort()` | Sorts in place |
| `xs.sort(key=func)` | Sorts in place using `func` to determine order |

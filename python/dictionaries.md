---
layout: default
---
# Dictionaries

[Official Documentation](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)

* Dictionaries associates keys with values
* Keys must be immutable (e.g. no lists, but tuples are ok)

## Creation

```python
# Literal
d = { key1 => value1, key2 => value2 }

# From list of pairs
d = dict([ (key1, value1), (key2, value2) ])
```

## Operations

| Syntax | Semantics |
|:-:|-|
| `xs[k]` | Read value associated with `k` |
| `xs[k] = v` | Add/overwrite value associated with `k` |
| `len(d)` | Number of key/value pairs in `d` |
| `d.keys()` | List of keys |
| `d.values()` | List of values |
| `d.items()` | Sequence of key/value pairs |
| `del(d[k])` | Removes key/value pair whose key is `k` |
| `d.clear()` | Empty dictionary |
| `d.copy()` | Make a copy |
| `k in d` | Checks if `k` is a key in `d` |

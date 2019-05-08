---
layout: default
---
# Lists

## Literals

```elixir
xs = [1, 2, 3]
ys = [ 1, 2 | [3, 4] ]
```

## Operations

| Syntax | Description |
|:-:|-|
| `hd` | Head |
| `tl` | Tail |
| `x in xs` | Membership |
| `xs ++ ys` | Concatenation |
| `xs -- ys` | Removes first occurrence of each `y` from `xs` |

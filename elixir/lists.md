---
layout: default
---
# Lists

* [Official documentation](https://hexdocs.pm/elixir/List.html)
* [Enum official documentation](https://hexdocs.pm/elixir/Enum.html#content)

## Literals

```elixir
xs = [1, 2, 3]
ys = [ 1, 2 | [3, 4] ]
```

## List Operations

| Syntax | Description |
|:-:|-|
| `hd` | Head |
| `tl` | Tail |
| `x in xs` | Membership |
| `xs ++ ys` | Concatenation |
| `xs -- ys` | Removes first occurrence of each `y` from `xs` |

## Indexing operations

| Syntax | Description |
|:-:|-|
| `Enum.at(xs, i, default \\ nil)` | Indexing, returns `elt` or `default` |
| `Enum.fetch(xs, i)` | Indexing, returns `{:ok, elt}` or `:error` |
| `Enum.fetch!(xs, i)` | Indexing, returns `elt` or raises exception |

## Looping Operations

| Syntax | Description |
|:-:|-|
| `Enum.all?(xs, f \\ id)` | Check if all `f(x)` are truthy |
| `Enum.any?(xs, f \\ id)` | Check if some `f(x)` is truthy |
| `Enum.count(xs, f)` | Count how many `f(x)` are truthy |
| `Enum.each(xs, f)` | Calls `f` for every `x` |
| `Enum.filter(xs, f)` | Returns those `x` where `f(x)` is truthy |
| `Enum.find(xs, default \\ nil, f)` | Finds first `x` for which `f(x)` is truthy |
| `Enum.find_index(xs, f)` | Index of first `x` for which `f(x)` is truthy, or `nil` |
| `Enum.flat_map(xs, f)` | Flattening of `[ f(x1), f(x2), ... ]` |
| `Enum.map(xs, f)` | `[f(x1), f(x2), ... ]` |
| `Enum.reduce(xs, f)` | Fold with `f(x, acc)` |
| `Enum.reduce(xs, init, f)` | Fold with `f(x, acc)` |
| `Enum.reject(xs, f)` | Returns those `x` where `f(x)` is falsey |
| `Enum.sum(xs)` | Returns sum |
| `Enum.with_index(xs, start_i)` | Pairs items up with index `{x[i], i}` |
| `Enum.zip(xss)` | Zips `xss` into list of tuples |
| `Enum.zip(xs, ys)` | Zips `xs` and `ys` into list of tuples |

## Misc Operations

| Syntax | Description |
|:-:|-|
| `Enum.drop(xs, n)` | Drops `n` first elements of `xs` |
| `Enum.join(xs, sep \\ "")` | Produces string |
| `Enum.length(xs)` | Length of `xs` |
| `Enum.max(xs, if_empty_func)` | Maximum |
| `Enum.max_by(xs, f, if_empty_func)` | Maximum |
| `Enum.min(xs, if_empty_func)` | Minimum |
| `Enum.min_by(xs, f, if_empty_func)` | Minimum |
| `Enum.random(xs)` | Random element from `xs` |
| `Enum.reverse(xs)` | Reverses order |
| `Enum.shuffle(xs)` | Shuffles order |
| `Enum.slice(xs, range)` | Returns slice |
| `Enum.slice(xs, start, len)` | Returns slice |
| `Enum.sort(xs)` | Sorts |
| `Enum.sort_by(xs, key_f, sorter_f \\ &<=/2)` | Sorts |
| `Enum.split(xs, n)` | Splits `xs` in two parts where first part contains `n` elements |
| `Enum.uniq(xs)` | Removes duplicates |
| `Enum.uniq_by(xs, eq_f)` | Removes duplicates |


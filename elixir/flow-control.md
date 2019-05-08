---
layout: default
---
# Flow Control

# case

```elixir
case x do
  []     -> ...
  [x|xs] -> ...
end
```

# cond

```elixir
cond do
  is_foo?(x) -> deal_with_foo
  is_bar?(x) -> deal_with_bar
end
```

# if

```elixir
if condition do
    ...
else
    ...
end

# Using keyword lists
if condition, do: ..., else: ...
```

# unless

```elixir
unless condition do
    ...
end
```

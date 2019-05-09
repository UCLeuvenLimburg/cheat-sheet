---
layout: default
---
# Functions

## Definition

```elixir
def foo(x, y, z) do
    ...
end
```

## Guards

```elixir
def foo(x, y, z) when cond1, do: ...
def foo(x, y, z) when cond2, do: ...
...
```

## Lambdas

```elixir
plus = fn (x, y) -> x + y end

# Shorthand notation
plus = &(&1 + &2)
```
---
layout: default
---
# Maps

[Official documentation](https://hexdocs.pm/elixir/Map.html)

## Literals

```elixir
%{ key1 => value1,
   key2 => value2,
   atom_key: value3 } # Shorthand notation for atom keys
```

## Lookup

```elixir
# Returns nil on missing key
value = map[key]

# If key is atom, raises on missing key
value = map.key
```

## Pattern Matching

```elixir
%{key: x} = %{key: 5}
# x is now bound to 5
```

## Updating

```elixir
# Only works for existing keys
map = %{x: 1, y: 2}
updated = %{ map | y: 3 }
# => updated is now %{ x: 1, y: 3 }
```
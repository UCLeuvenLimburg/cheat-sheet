---
layout: default
---
# Streams

[Official documentation](https://hexdocs.pm/elixir/Stream.html)

## Construction

```elixir
Stream.map(1..1000, & &1)
# => 1, 2, 3, ..., 1000

Stream.cycle([1, 2, 3])
# => 1, 2, 3, 1, 2, 3, 1, 2, 3, ...

# Generator function
Stream.iterate(0, & &1+1)
# => 0, 1, 2, 3, 4, ...
```
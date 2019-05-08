---
layout: default
---
# Sigils

## Built-In

| Syntax | Description |
|:-:|-|
| `~r'...'` | Regular expression |
| `~s'...'` | String |
| `~S'...'` | Raw string |
| `~c'...'` | Character list |
| `~w'...'` | Word list |
| `~W'...'` | Raw word list |
| ~s'''...''' | Heredoc |

## Delimiters

```elixir
~r/.../
~r|...|
~r"..."
~r'...'
~r(...)
~r[...]
~r{...}
~r<...>
```

## Custom sigils

```elixir
defmodule MySigils do
    def sigil_a(string, [?d]), do: String.to_integer(string) * :math.pi / 180
    def sigil_a(string, [?r]), do: String.to_integer(string)
end

import MySigils

~a(90)d
```
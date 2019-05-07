---
layout: default
---
# Operators

## Arithmetic

| Syntax | Semantics |
|-|-|
| `x + y` | Addition |
| `x - y` | Subtraction |
| `x * y` | Multiplication |
| `x / y` | Division (floating point) |
| `div(x, y)` | Integer division |
| `rem(x, y)` | Remainder division |
| `:math.sqrt(x)` | Square root |
| `:math.pow(x)` | Power |

## Comparison

| Syntax | Semantics |
|-|-|
| `x == y` | Equality |
| `x === y` | Strict equality |
| `x != y` | Inequality |
| `x !== y` | Strict inequality |
| `x < y` | Less than |
| `x <= y` | Less than or equal to |
| `x > y` | Greater than |
| `x >= y` | Greater than or equal to |

## Booleans

| Syntax | Semantics |
|-|-|
| `a or b` | Strict disjunction (only on `true` and `false`) |
| `a and b` | Strict conjunction (only on `true` and `false`) |
| `not a` | Strict negation (only on `true` and `false`) |
| `a || b` | Disjunction on generalized booleans |
| `a && b` | Conjunction on generalized booleans |
| `!a` | Negation on generalized booleans |

## Lists

| Syntax | Semantics |
|-|-|
| [x|xs] | List construction |
| `xs ++ ys` | List concatenation |
| `x in xs` | List membership |
| `x not in xs` | List membership negation |

| Syntax | Semantics |
|-|-|
| `s1 <> s2` | String concatenation |
| `s =~ regex` | Regex match |

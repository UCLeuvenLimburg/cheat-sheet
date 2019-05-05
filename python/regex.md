---
layout: default
---
# Regular Expressions

[Official Documentation](https://docs.python.org/3/library/re.html)

## Functions

| Function | Description |
|-|-|
| `re.search(r, s)` | Looks for a substring of `s` that matches `r` |
| `re.match(r, s)` | Looks for a prefix `s` that matches `r` |
| `re.fullmatch(r, s)` | Checks if `s` matches `r` in its entirety |
| `re.split(r, s)` | Splits `s` using separators described by `r` |
| `re.findall(r, s)` | Finds all substrings in `s` matching `r` |
| `re.sub(r, repl, s)` | Replaces all substrings of `s` matching `r` by `repl` |

| Option | Description |
|:-:|-|
| `DOTALL` | `.` also matches newlines |
| `MULTILINE` | `^` and `$` also match immediately after and before newlines, respectively | `IGNORECASE` | Case insensitive matching |

## Regex Syntax

| Character | Description |
|:-:|-|
| `.` | Matches anything except newline (see DOTALL) |
| `^` | Matches start of string (see MULTILINE) |
| `$` | Matches end of string (see MULTILINE) |
| `p*` | 0 or more repetitions of `p` |
| `p+` | 1 or more repetitions of `p` |
| `p?` | Optional `p` |
| `p{m}` | `m` repetitions of `p` |
| `p{m,n}` | `m` to `n` repetitions of `p` |
| `p|q` | Matches either `p` or `q` |
| `[...]` | Character class |
| `\d` | Digit |
| `\D` | Nondigit |
| `\w` | Word character (letter of underscore) |
| `\W` | Nonword character |
| `\b` | Word boundary |
| `\s` | Whitespace character |
| `\S` | Nonwhitespace character |
| `\A` | Beginning of string |
| `\Z` | End of string |

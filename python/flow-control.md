---
layout: default
---
# Flow Control

## Conditional

```python
# If statement
if cond:
    ...
elif cond:
    ...
else:
    ...

# If expression
result = a if cond else b
```

## Loops

```python
while cond:
    if cond:
        continue # Jump back to beginning of loop
    if cond:
        break # Escape the loop
```

```python
for x in xs:
    ...
```

## Examples

```python
# Repeat 10 times
for _ in range(10):
    ...

# Iterate over list
for x in [1, 2, 3, 4]:
    ...

# Iterate over dictionary
for key, value in dictionary.items():
    ...
```

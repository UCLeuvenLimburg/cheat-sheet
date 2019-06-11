---
layout: default
---
# IO

## Reading Files

```python
# Opening a file for reading
with open(filename) as file:
    # Use file

# Reading entire contents as a single string
with open(filename) as file:
    contents = file.read()

# Iterating over lines, one by one
with open(filename) as file:
    for line in file:
        # Process line
```

## Writing Files


```python
# Opening a file for writing
with open(filename, 'w') as out:
    # use out

# Writing to file
with open(filename, 'w') as out:
    out.write(string)  # Does not add newline!

# Writing to file using print
with open(filename, 'w') as out:
    print(string, file=out) # Does add newline!
```

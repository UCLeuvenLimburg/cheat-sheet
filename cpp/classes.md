---
layout: default
---
# Classes

## Declaration

```cpp
class Movie
{
    std::string title;
    int runtime;

public:
    Movie(const std::string&, int);
    ~Movie();

    int getRuntime() const;
    void setRuntime(int);
};
```

## Constructor

```cpp
Movie::Movie(const std::string& title, int runtime)
  : title(title), runtime(runtime) { }
```

## Destructor

```cpp
Movie::~Movie()
{
    // Clean up
}
```

## Member Function Definition

```cpp
int Movie::getRuntime() const
{
    return runtime;
}
```

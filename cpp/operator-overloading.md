---
layout: default
---
# Operator Overloading

[Operator overloading](https://en.cppreference.com/w/cpp/language/operators)
lets you define new meanings for the following operators:
`+`  `-` `*`  `/` `%` `^`  `&` `|`
`~` `!` `=` `<` `>` `+=` `-=` `*=` `/=` `%=` `^=` `&=` `|=` `<<` `>>` `>>=` `<<=`
`==` `!=` `<=` `>=` `<=>` `&&` `||` `++` `--` `,` `->*` `->` `()` `[]` `co_await`
`new` `new[]` `delete` `delete[]`

## As Member Function

* The first operand must have the type of the containing class.
* This approach cannot therefore not be used for binary
  operators whose left operand is not the containing type.
  Example: `<<` for writing to output streams.


```cpp
struct Fraction
{
    // Left operand is *this
    Fraction operator +(const Fraction& right) const
    {
        // Add *this to right and return result as a new object
    }
};
```

## As Non-Member Function

```cpp
struct Fraction
{
    ...
};

Fraction operator +(const Fraction& left, const Fraction& right)
{
    // Add left and right and return result as a new object
}
```

Certain operators cannot be defined as non-member functions: `=`, `()`, `[]`
and `->`.

## Stream Operators

```cpp
std::ostream& operator <<(std::ostream& out, T x)
{
    // Write x to out

    return out;
}
```

```cpp
std::istream& operator >>(std::istream& in, T& x)
{
    // Read x from in

    return in;
}
```

## Operator ->

The arrow operator can be seen as a unary operator:
`a->m` calls `operator ->` successively on `a`,


```cpp
struct Foo
{
    // T is either a raw pointer or an object supporting ->
    T operator ->() { }
};
```

## Literals

[User-defined literals](https://en.cppreference.com/w/cpp/language/user_literal)
let you introduce literals for your own types.

```cpp
double operator "" _degrees(long double x)
{
    return x * 3.141592 / 180;
}

double alpha = 30_degrees;
```

## Casts
[User-defined conversion](https://en.cppreference.com/w/cpp/language/cast_operator)
lets you specify how to cast your types to other types. Casts
can be implicit and explicit.

```cpp
class Fraction
{
    int numerator, denominator;

public:
     operator std::string() const
     {
        std::stringstream ss;
        ss << numerator << "/" << denominator;
        return ss.str();
     }

    explicit operator double() const
    {
        return double(numerator) / denominator;
    }
};

Fraction f(3, 4);

std::string str = f;               // implicit cast to string is ok
double x = f;                      // implicit cast not ok
double y = static_cast<double>(f); //  ok
```

## Examples

```cpp
struct Fraction
{
    int numerator, denominator;

    Fraction operator *(const Fraction& right) const
    {
        int n = numerator * right.numerator;
        int d = denominator * right.denominator;

        return Fraction { n, d };
    }

    Fraction& operator *=(const Fraction& right)
    {
        return (*this = *this * right);
    }

    Fraction& operator =(const Fraction& right)
    {
        numerator = right.numerator;
        denominator = right.denominator;
    }

    bool operator ==(const Fraction& right) const
    {
        return numerator == right.numerator && denominator == right.denominator;
    }

    bool operator !=(const Fraction& right) const
    {
        return !(*this == right);
    }

    bool operator <(const Fraction& right) const
    {
        return static_cast<double>(*this) < static_cast<double>(right);
    }

    bool operator <=(const Fraction& right) const
    {
        return *this < right || *this == right;
    }

    bool operator >(const Fraction& right) const
    {
        return !(*this <= right);
    }

    bool operator >=(const Fraction& right) const
    {
        return !(*this < right);
    }

    explicit operator double() const
    {
        return double(numerator) / double(denominator);
    }
};
```

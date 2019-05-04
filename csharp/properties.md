---
layout: default
---
# Properties

## Long version

```csharp
class Foo
{
    // Actual field where data is stored
    private int field;

    public int Field
    {
        get // Getter
        {
            return this.field;
        }
        set // Setter
        {
            if ( !IsValidValue(value) )
            {
                throw new Exception();
            }
            else
            {
                this.field = value; // value refers to the value being assigned to Field
            }
        }
    }
}
```

Usage:

```csharp
var foo = new Foo();

int value = foo.Field; // calls getter
foo.Field = 5; // calls setter with value=5
```

## Shorter version

If the getter/setter simply return/set the field (e.g. no validation),
you can use this shorter syntax.

```csharp
class Foo
{
    // Implicitly defines a backing field
    public int Field { get; set; }
}
```

## Readonly Property

```csharp
class Foo
{
    public Foo()
    {
        this.Field = 0; // Constructor can set value, but no one else
    }

    public int Field { get; }
}
```

## Computed Property

```csharp
class Person
{
    public int Age { get; set; }

    public bool IsMinor => Age < 18;
}

var person = new Person() { Age = 15 };
var b = person.IsMinor; // true
```
---
layout: default
---
# Types

```typescript
boolean
number
string
T[]                // Array
[T1, T2, T3, ...]  // Tuple
any
void
null
undefined
never
object
(x1 : T1, x2 : T2) => R  // Function
T1 | T2    // Union
"a"        // String literal type
1          // Integer literal type
keyof T    // Index type query operator

// Index types
interface Foo
{
    [key : string] : T
}

type Readonly<T> = {
    readonly [P in keyof T] : T[P];
}

type Partial<T> = {
    [P in keyof T] ?: T[P];
}
type Pick<T, K extends keyof T> = {
    [P in K] : T[P];
}

type Record<K extends keyof any, T> = {
    [P in K] : T;
}

type ParameterTypes<T> = T extends (...args : infer Ps) => infer _R ? Ps : never;

type ReturnType<T> = T extends (...args: any[]) => infer R ? R : never;
```

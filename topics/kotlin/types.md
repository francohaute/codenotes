# Types in kotlin
TODO

- What is Any?

## Primitives

Kotlin doesn't have primitives like java. It comes with [first class objects](./objects.md)
equivalent to the primitives that java has.
The action of wrapping a primitive inside an object is call *boxing*.
So it works like a wrapper: when generics or nullability is required the compiler
will convert them to the primitive equivalent for performance.

**There is no distinction between the object type and the primitive (unlike java).
Also, two different values that are boxed might not use the same instance,
so referential equality is not guaranteed on boxed values.**

## Chars

The char type is not treated as a number, as used in java.
The implications of this decision are:
1. There are no implicit conversion to numbers.
2. Arithmetic operators are not allowed. To sum two char, first you need to 
   explicitly convert it with the proper conversion function.
3. Comparisons are based on character encoding.

## Numbers

Kotlin does not support automatic widening of numbers, so conversion must be 
invoked explicitly.

## Strings 

Strings provide an iterator that can be use in a for loop.

## Arrays

Unlike java, arrays in kotlin are not treated as special, just as a regular collection
class.

For performance optimization and memory efficiency, kotlin provides specialized
arrays classes of each of the primitive types supported by the jvm.

## Smart casting

# Golang

## To learn

### Advance 

- Complex numbers

## Types

- how does the type convertion works?
- literals are untype:
    - what does it mean?
    - what does it allow you to do?
- Go does not support method overloading. You can name two methods equal only if 
  the type receiver is different.
- Also the methods must be declare in the same package as the type receiver.
- When to use type or pointer receiver?
- When using a pointer receiver, go autommatically takes the address of the value. 
  The inverse happen when you call a type receiver on a pointer, go dereference 
  the pointer and call the function.
- What happen if you call a value receiver method on a nil pointer instance?
- And if you call a pointer receiver method on a nil pointer instance?
- Go encourage to not use getter and setter for everything (like java), just for 
  cases in wich you need to update multiple fields or when the update isn't a straight 
  assignment.
- method values and expressions.
- Does golang has inheritance?
- Types are executable documentation.
- Embedded fields:
    - You can embed a type inside another type by not naming it when declaring 
      the container type. This way, you then can access the embed type content 
      by just calling the content fields on the container. Unless you have two 
      fields (one in the inner and one in the outer) name the same.
    - It doesn't work as inheritance.
    - In case you have two methods or fields named the same, the outer type will be 
      called. The exception is when you call a method of the inner type that calls 
      another method in that inner type that has the same name as another method 
      in the outer type. In that the case, the inner method will be called.
- Type assertion:
    - Reveal the type of the value stored in the interface.
    - Check at runtime. If one fails then it panics.
- Type conversion:
    - Check at compile time, except between slices and arrays.
- Type switch.
- When to use type assertion and conversion?

### Generics

- Why sometimes you need generics instead of interfaces?
- to return the zero value for a generic, first initialized it with var and then 
  return that variable.
- The comparable interface.
- Underlying types.

### Interfaces

- What does it mean that interfaces are implicit?
- Embedded interfaces.
- Functions should take interfaces and return structs. But, keep in mind that 
  invoking a function with interface parameters require a heap allocation for 
  each parameter. So, you have to make a choice between better abstraction and 
  better performance.
- Empty interfaces and any. Avoid it.

### iota

- Only use iota when the constants are referred by name rather than by value. 
  If the value matters, then specify it explicitly.
- How does iota works?
- What happens when the const declaration has no type and value asigned?

### Literals 

- default types for literal values (implicit type)
- unread variables and constants

### Numbers

- Floating-point:
    - what does a non zero divided by zero value returns?
    - an 0 by 0?
    - variance (epsilon) when comparing two values?

## Arrays

- The size of the array is also part of it's type
- you can use constants for declaring the size of an array. obviusly you can't use 
  a variable since the compiler can't know its value at compile time.
- only use arrays when you already know the size that you are returning and don't 
  expect it to grow
- converting a slice to an array without specifying the size gives a compile-time 
  error. And if you specify an array size that is bigger than the slice it will panic.

### Slices

- What is the zero value for a slice?
- Can you compare a slice?
- how can you append two slices?
- how does a slice grow?
- what would happen if you append a value to a slice populated with zeros at 
  initialization? and if it has a size of 0?
- Specifying a capacity smaller than the size of the len is a compile with a constant 
  or literal, it will trow a compile-time error. If you do it with a variable the
  program will panic at runtime.
- is a nil slice the same as a slice with 0 size and 0 cap? Favor nil slices, so 
  you can use comparison
- Slices of slices

## Strings

- Strings are arrays of bytes
- when slicing a string, you are indexing bytes so beware when using multi-bytes 
  unicodes like emojis
- you can convert a rune to a string and a string to an array of runes or bytes.

## Maps

- They are like slices in many ways. They are comparable only to nil (wich is 
  it zero value)
- The key must always be a comparable type.
- The map in go is a hashmap
- How to check is a key exists?
- how to use the map as a set?

## Structs

- if you initialize a struct without using field names, if a future version add 
  fields then it will not compile
- Are structs comparable?

## Control structures

- for:
    - var is not legal for initialization, only :=
    - when iterating over a map, the order is random
    - when iterating a string, it does it over the runes, not the bytes. 
      So in case the runes is more than one byte, there are gonna be skipped index.
    - Since go 1.22 the value and index are copied.
- switch:
    - you can switch any type that can be compared using ==
    - there is no fallthrough

## Functions

- go doesn't have optional nor named parameters. What should you use then? and why?
- variadic parameters. how to use it?
- multiple return values
- ignored return values
- named return values: what happen if you have return values but you return a blank
- functions as variable. what is the zero value?
- function type declaration
- annonymous functions: also known as closures
- functions as parameters
- defer functions. What is? If multiple, how does the order goes? 
  Cool to use when you want to force someone to run a function after they called 
  a function to make that function return a function.

## Pointers

- the zero value for a pointer is nil. The program will panic if you try to 
  dereference a nil pointer.
- The new function.
- You can't use the adress operator before a literal or a constant.
- best practices for when passing or not a pointer as parameter? And when returning 
  or not?


# C types

## implicit (or inferred) and explicit types

An implicit type is one that is not explicitly assigned rather it is inferred 
by the compiler according to the value of the variable.

Before c99, a variable or function declared without a type was defaulted to an 
int.

There are two cases in wich the types are inferred:
- Integer promotion: Smaller types (short and char) are promoted to int when used 
  in expressions.
- Arithmetic conversions: the type of the operand is adjusted to the wider type 
  to avoid data loss.

***Always declare types explicitly to avoid problems.***

### Typecasting

A variable type can be converted into another, either implicitly by how it is 
used or explicitly with typecasting.

## Sizes

### sizeof()

Is a built-in function that returns the size of the passed data type.

## Enums

You can use unnamed enums to declare literal constants but only for integer values.

## Structures

User-defined type.

The size of a structure is the smallest even multiple of the size of its largest
component that fits all the other components. This is called structure alignment.
The padding can occur in any position and in whatever division of the hole size.
You shouldn't worry about padding. However, because of this you can't compare
two structures as hole entities, instead use a function that uses the components
to compare.

## typedef()

The main purpose is to create synonims of types so the code is more readable.
The other main advantage is that you can change the base type of all the variables
that use the synonim by just changing it in the type definition line.

## Arrays

There is two types of arrays:
- Constant-lenght: an arrays whose size was determined by a constant. It's check 
  at compile time so it can detect out of bound errors.
- Variable-lenght: array whos size is not know until runtime. The size cannot 
  be check at compile time since the value can change in the middle of the execution.

Arrays declared with const type is still a variable lenght array.

Constant arrays allows easier initialization.

When passing an array as argument, if it is a variable lenght array it must have 
an asteriks between the brackets.

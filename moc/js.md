# JavaScript

TODO

- Events
- Array functions
- objects

## Strict mode

- Is a way to opt-in to a restricted variant of the language.
- Restrictions: 
  - ReferenceError: When trying to create a global out of an undeclared variable 
    initialized with a value it throws an error.
  - You cannot name variables using the words "eval" or "arguments".
  - TODO

## Variables and constants

- With no operator you can define a global variable at any scope.
- var: 
  - No longer used. Maybe in old libraries.
  - It allows redundant declarations.
  - It defines the variable at the top the current scope where it is initialized. 
    It is called **Hoisting**
- let: 
  - It is block scoped.
  - does not allow redundant declarations unless, the scope is different.
  - Is not hoisted. This create what is known as temporal dead zone, that is the 
    space between the start of a function and the declaration of the variable, any 
    reference here will throw a ReferenceError. Beware that javascript engine will 
    be aware of the variable even in the temporal dead zone but this variables 
    will be unable to be refereced until the declaration.
- const:
    - Same as let is most things.
    - You can use it in for loops, but you cant modify it. You can make use of 
      the fact that every iteration creates a new const and use it with arrays 
      and keymaps.
- undeclared variables:
    - only one operation can be performed on an undefined variable and is typeof.
    - the typeof return undefined on undeclared variables
- It is recommended to always initialize variables so when typeof returns undefined 
  you know is because the variable hasn't been defined.

## Data types

- typeof operator:
    - the typeof null is object since it null represent an empty object reference
- undefined:
    - when a variable is defined but not initialized.
    - There is an undefined value that is equivalent but it's use is only meant 
      for comparisons.
    - undefined is not the same as undeclared.


### Naming

- case-sensitive
- camelCase

## Operators

- the comma operator:
    - evaluate multiple expressions but return only the last one

## Strings

- Using backsticks you can declare a string using templates `${variable}` (like kotlin).
- Backsticks also allow multiline.

## Functions

- default parameters and optional.
- anonymous functions and arrow functions
- function expressions and declarations - scope
- js call-stack:
    - whenever a function is called, the engine creates a function execution 
      context, pushes it to the top of the stack and start executing it.

## Arrays

- The difference between an array and an object is that the array uses a numbered 
  index rather than a named index.

## objects



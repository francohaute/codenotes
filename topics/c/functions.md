# C functions 

#c
#functions

C consist on functions that are compiled into a single program.

## Main function 

It's the function that is called by the system every time the program is runned.
The function identifier is pre-defined, so no other function can be called main.
Also you can't call the main function, only the system can.

## Function signature

Is the union of the function identifier (it's name), the function parameter list
and the function type (what it returns).

In some languages is the function signature what is used to identify a function.
In the case of C, only the function identifier is used, so every function name 
must be different.

The function identifier is case-sensitive.

## Function prototypes

It's a function declaration without the body that allows to use the function 
before the function block. The function signature must match either a 
compile error will be trown.
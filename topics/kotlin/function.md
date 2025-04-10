# Functions in kotlin
TODO
When reformatting a kotlin function, make sure you reformat using the rename or
change signature options, instead of just change it manually, since it will 
change the argument names and signature in the files that use that function.

## vararg

Keyword used to declare a function that allows multiple arguments of the same type.


## Extension functions

You can create functions that work on objects of an already existing class without 
having to modify that class.

It works declaring a function especifing a receiver type (the class you want to
extend) and you would have access to a receiver object (the instance of the class
you are extending.

```kotlin
fun String.lastChar(): Char = this.get(this.length - 1)
```

The class "String" is the receiver type and "this" reference the receiver object.
You can access public variables and member functions (you dont have to use "this")
but you can't access private members.

Extension functions can be used on any type declared on a language that uses the
JVM.

Extension functions are compile into a class with the name of the file they are 
declared in (capitalized and postfixed with "Kt") and declared as static. So, you
can access them from wherever you want to call it.

If a member function and a extension function have the same signature, the member
one will be called.

### Extension functions of companion objects

You can declare an extension function of a companion object.

```kotlin
class Person(val firstName: String, val lastName: String){
    companion object{}
}

fun Person.Companion.fromJSON(json: String): Person{}
```

## Infix functions

An infix function is a function that can be called putting the name of the function
just in the middle between the object and the argument of the function. It only 
allow one required argument.

## Local functions

In order to not repeat code, you can use local functions that are defined inside
a function. 
Local functions have full access of the enclosing functions parameters and local
variables.


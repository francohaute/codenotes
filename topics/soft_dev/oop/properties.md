# Properties

A property is the combination of a field and his accessors. They are used to manage
the state of a class by storing data relevant to it.

## Management

### Backind fields
 
It's the hidden storage used by properties to store their values. It's mostly 
used when using a custom setter or getter.
Backind fields help maintain encapsulation since it allows access to the property's
value access and management without exposing the internal storage mechanism.

```kotlin
class Person {
    var name: String = "Unknown"
        get() = field
        set(value) {
            field = value
            println("Name has been changed to $value")
        }

    var age: Int = 0
        set(value) {
            if (value > 0) {
                field = value
            } else {
                println("Age cannot be negative or zero")
            }
        }
}
```

### Backing property

It's the use of another property to back the main property. It's used mainly when
you need a more complex form of encapsulation or to manage aditional aspects of
the data that shouldn't be exposed in the main property(managing dependencies 
between multiple properties or maintaining an invariant).

```kotlin
class Person {
    // Backing property
    private var _age: Int = 0

    // Public property with custom getter and setter
    var age: Int
        get() = _age
        set(value) {
            if (value > 0) {
                _age = value
            } else {
                println("Age cannot be negative or zero")
            }
        }
}

fun main() {
    val person = Person()

    // Setting a valid age
    person.age = 25
    println("Age: ${person.age}")  // Output: Age: 25

    // Attempting to set an invalid age
    person.age = -5                // Output: Age cannot be negative or zero
}
```

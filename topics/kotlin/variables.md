# Kotlin variables

## "val" inmutabillity

In Kotlin, `val` is a keyword used to declare read-only (immutable) variables.
When you declare a variable using `val`, it means that you cannot reassign a 
new value to that variable once it's initialized. However, it's important to 
note that while `val` ensures that the reference to the object cannot change, 
it does not guarantee that the object itself is immutable.

In other words, if you have a `val` referencing a mutable object (e.g., a list 
or a mutable data class instance), you can still modify the properties or 
contents of that object. The immutability applies only to the reference, not
to the object it points to.

For example:

```kotlin
val list = mutableListOf(1, 2, 3)
list.add(4) // This is allowed

val person = Person("John", 30)
person.age = 31 // This is allowed if 'age' is a mutable property of the Person class
```

In the above example, `list` and `person` are declared with `val`, which means 
you cannot reassign them to reference a different object. However, you can 
still modify the contents of `list` and the properties of `person` because 
they are mutable objects.

If you want to ensure immutability of an object itself, you need to make sure 
that the object is immutable or use immutable collections (e.g., `listOf()` 
instead of `mutableListOf()`). Additionally, Kotlin provides data classes with 
`val` properties, which automatically generate immutable data classes, 
ensuring immutability at the object level.

## Properties [note](../soft_dev/oop/properties.md)

In kotlin, each property comes with a default getter and in the case of mutable 
variables with a default setter. You can define custom accessors and delegate 
the accessors logic to another class.
It also supports access to [backind fields](../soft_dev/oop/properties.md#backind-fields) by using the `field` keyword in custom
getter. That identifier can only be used inside the accessor of the property.

### Delegated properties

You can declare a object and delegate it's initialization and setter and getters
to another object.

```kotlin 
import kotlin.reflect.KProperty

class ExampleClass{
    
    private val arguments = mutableMapOf<String, MutableDelegate<*>>()

    // Adds an argument and returns a delegate
    fun <T> add(initialValue: T): MutableDelegate<T> {
        val delegate = MutableDelegate<T>(initialValue)
        arguments[initialValue.toString()] = delegate
        return delegate
    }

    // Simulates parsing and assigns a new value to the delegate
    fun parse() {
        // Simulate parsing and update the values of the delegates
        // In a real scenario, you'd probably process 'args' or similar
        arguments.forEach { (key, delegate) ->
            if (key == "hola") {
                @Suppress("UNCHECKED_CAST")
                (delegate as MutableDelegate<String>).value = "Parsed String Value"
            }
        }
    }

}

// Custom delegate class that holds a value
class MutableDelegate<T>(initialValue: T){

    var value: T = initialValue

    operator fun getValue(thisRef: Any?, property: KProperty<*>): T {
        return value
    }

    operator fun setValue(thisRef: Any?, property: KProperty<*>, value: T) {
        this.value = value
    }
}

fun main(args: Array<String>) {
    val example = ExampleClass()
    val argument by example.add("hola")
    example.parse()
    println(argument)  // Outputs: Parsed String Value
}

```

TODO hard: go deep and make a command line parser

### Top-level properties

By default top-level properties are exposed to java code as accessors (a getter 
for a val and both setter and getter for var). If you want to expose a constant 
to java as "public static final" then you can use the 'const' modifier (only allowed
for primitive types and String).

### Extension properties

Just like extension functions, you can declare extension properties. It allow
you to extend classes with an API that can be accessed using property syntax.
Even tough they are called properties, they can't have any state, because there is
no place to store it, since it's not possible to add extra fields to existing
instances of objects.


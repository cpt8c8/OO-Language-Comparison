# OO-Language-Comparison
## Kotlin Vs. Go
## Samantha Trenholm and Matt Tschannen

### Language purpose/genesis
#### Why was the language created?
##### Kotlin
Kotlin was developed by JetBrains primarily for internal use. It was intended to boost productivty and improve workflow, which would result in improved sales.
##### Go
Go was designed by engineers at google with the purpose of creating a language that would resolve a lot of common criticisms of popular languages while maintaining the strengths that had made them so popular. 

#### What problems was the language trying to address?
##### Kotlin
JetBrains was looking for a language that adresses their needs, had fast compile times, was streamlined, and could ineract with and replace Java.
##### Go
Some specific goals for Go were creating a language that supported static typing and was easily scalable like Java, didn't require a lot of boilerplate like Ruby or Python, and - what I see as the most powerful aspect of go - had good support for networking and multiprocessing.

#### Is the language a reaction to a previous language or a replacement for another language?
##### Kotlin
It was largely intended, as mentioned above, to be a replacement for Java.
##### Go
The creation of Go was certainly a reaction to shortfalls the creators saw with a lot of contemporary languages, especially C++.

### Unique features of the language
#### Does the language have any particularly unique features?
##### Kotlin
One of Kotlin's most loved features is its null safety, which protects it from null pointer exceptions. By using its simple ? operator, it first checks the value to see if it is null or not. If it’s not null then only then it will perform the next operation. It is used as shown. 

```kotlin
val str:String? = "name"
```

Other things of note include that Kotlin is completely inter-operable with Java, its ability to return multiple values, that it does not require a ";" at the end of a line, and the ability to have default and named arguments (as shown below).
```kotlin
fun example(num: Int, str: String = "9") {}

example(15, "Hey")

example(str = "Name", num = 45) //Named argument

example(45) //usage of default argument
```
##### Go
One interesting feature of go is its concurrency features, namely the use of goroutines and channels. These features allow for code to be optimized for parallelism and asynchrony with ease. Any function can be called as a goroutine in Go, and Go will automatically handle whether or not a new thread should be started or if it would be more efficient to execute the operation on an existing thread. This minimizes excessive Thread creation which can actually slow down your program,  because despite the advantages of parallel processing thread creation is a fairly expensive task. To allow for these go routines to exchange information asynchronously, Go supports the use of channels which provide a FIFO storage entity that goroutines can use to drop off and pick up information when they are ready to do so.

```go
func worker(done chan bool) {
    fmt.Print("working...")
    time.Sleep(time.Second)
    fmt.Println("done")

    done <- true
}
func main() {

    done := make(chan bool, 1)
    go worker(done)

    <-done
} 
```

### Name spaces
#### How are name spaces implemented? 
##### Kotlin
Kotlin follows Java's naming conventions. Names of packages are always lower case and do not use underscores, names of classes and objects start with an upper case letter and use camel humps, names of functions, properties and local variables start with a lower case letter and use camel humps and no underscores (with the exception of factory functions used to create instances of classes, which can have the same name as the class being created), and names for tests (and only tests) can have method names with spaces enclosed in backticks. The naming conventions for properties are as follows: names of constants should use uppercase underscore-separated names, names of top-level or object properties which hold objects with behavior or mutable data should use regular camel-hump names, names of properties holding references to singleton objects can use the same naming style as object declarations, and for enum constants, it's OK to use either uppercase underscore-separated names (enum class Color { RED, GREEN }) or regular camel-humps names starting with an uppercase letter, depending on the usage.
##### Go

#### How are name spaces used?
##### Kotlin
Kotlin's namespaces are implemented very similarly to Java. The package is described at the top of the document with imports (typically) below it, as such.
```kotlin
package foo.bar
import foo.*
```
##### Go

    
### Types
#### What types does the language support?
##### Kotlin
Kotlin can represent numbers through the types Byte, Short, Int, Long, Float, and Double. It also supports Char, String, and Boolean. 
##### Go
Go supports several basic int, float and string types, as well as derived types. Many more types are available through the go/types library and others. 

#### Are both reference and value types supported?
##### Kotlin
Kotlin supports both reference and value tyoes.
##### Go
Reference and value types are both supported, keeping in line with Go’s C heritage.

#### Can new value types be created?
##### Kotlin
Kotlin does not facilitate the creation of basic types.
##### Go
New concrete types can certainly be created through structs, but there isn’t support to create additional basic types.
    
### Classes
#### Defining
##### Kotlin
Classes are easily defined in Kotlin, as show below.
```kotlin
class Example {
    // ...
}
```
##### Go
The syntax for creating structs in go is similar to C. Refer to the code below for proper struct definition.
```go
type person struct {
    name string
    age  int
}
```
#### Creating new instances
##### Kotlin
A instance of a Class can be created as shown below.
```kotlin
val ex = Example()
//or
val exXx = ExXxample("Like that Vin Diesal movie")
```
##### Go

#### Constructing/initializing
##### Kotlin
Kotlin allows for both a primary constructor and mutiple secondary contructors. A primary constructor is placed in the class header as shown.
```kotlin
class Example constructor(exOne: String) {
}
```
However, the primary constructor cannot contain code. 
Secondary constructors are declared as show. 
```kotlin
class Example {
    constructor(parent: Example) {
        parent.children.add(this)
    }
}
```
All secondary constructors must delegate to the primary constructor (if it exists) using "this". 
```kotlin
class Example(val exOne: String) {
    constructor(exTwo: String, parent: Example) : this(name) {
        parent.children.add(this)
    }
}
```
##### Go

#### Destructing/de-initializing
##### Kotlin
Objects in Kotlin can be destructured into multiple values.
```kotlin
val (variableOne, variableTwo) = example 
```
This leaves us with two newly declared variables.
##### Go

#### Instance reference name in data type (class)
##### Kotlin
In Kotlin this is done through secondary constructors, as discussed above. It is also shown below again.
```kotlin
class Example(val exOne: String) {
    constructor(exTwo: String, parent: Example) : this(name) {
        parent.children.add(this)
    }
}
```
##### Go

### Properties
#### Getters and setters…write your own or built in?
##### Kotlin
Getters and setters are built in for Kotlin and are used as shown.
```kotlin
fun main(args: Array<String>) {
    val ex = Example()
    ex.exValue = "New Value"
    println("${ex.exValue}")
}

class Example {
    var exValue: String = "defaultValue"
    
    //the following are not required
    //get() = field

    //set(value) {
        //field = value
    //}
}
```
You can also have custom setters and getters if you would like.
```kotlin
class Example(exOne: Int, exTwo: String, exThree: Int) {
    val exampleOne: Int = exOne

    var exampleTwo: String = exTwo 
        // Custom Getter
        get() {     
            return field.toUpperCase(
        }     

    var examplethree: Int = exThree
        // Custom Setter
        set(value) {
            field = if(value =! 0) value else throw IllegalArgumentException("exThree must be zero")
        }
}
```
##### Go

#### Backing variables?
##### Kotlin
In Kotlin you have backing fields, which help you refer to the property inside the getter and setter methods. You must use them becuase using the property directly inside the getter or setter causes a recursive call which will generate a StackOverflowError. The Kotlin code in the getters and setters example has these in use (the fields have been named "field" for ease of identification). 
##### Go

#### Computed properties?
##### Kotlin
Kotlin allows for the use of delegated properties, with a syntax as show,
```kotlin
class Example {
    var ex: String by Delegate()
}

class Delegate {
    operator fun getValue(thisRef: Any?, property: KProperty<*>): String {
        return "$thisRef, thank you for delegating '${property.name}' to me!"
    }
 
    operator fun setValue(thisRef: Any?, property: KProperty<*>, value: String) {
        println("$value has been assigned to '${property.name}' in $thisRef.")
    }
}
```
So, the get() and set() of the property "ex" are delegated to the getValue() and setValue() methods of the "Delegate()" class. Kotlin's standard library contains a few very helpful standard delegates such as Lazy() (for if the value gets computed only upon first access) and Delegates.observable() (listeners that get notified about changes to this property). 
##### Go

    
### Interfaces / protocols
#### What does the language support?
##### Kotlin
Kotlin does support interfaces, and they are implemented very similarly to Java 8. A class can implement many interfaces.
##### Go

#### What abilities does it have?
##### Kotlin
Kotlin interfaces can contain declarations of abstract methods and method implementations. However, they cannot store state. They can have properties as long as they are abstract or provide accessor implementations.
##### Go

#### How is it used?
##### Kotlin
Interfaces in Kotlin are implemented as shown.
```kotlin
interface ExampleInterface {
    fun foo()
    fun bar() {
      // body if desired
    }
}

class Child : ExampleInterface {
    override fun foo() {
        // body
    }
}
```
##### Go

### Inheritance / extension
#### Kotlin
Inheritance in Kotlin is similar to inheritance in Java. A class the extends another is declared as such:
```kotlin
class SuperClass{
//...
}

class SubClass : SuperClass {
//...
}
```
For a subclass to override a method in a superclass, the method in the superclass must be strictly annotated as overridable (using the open modifier).
```kotlin
open class Super {
    open fun foo() {}
    fun bar() {}
}
class Sub() : Super() {
    override fun foo() {}
}
```
The overriding of properties is handled the same way. In order to call the superclass implementation of a function, you would use the "super@" modifier as shown.
```kotlin
class Sub : Super() {
    override fun f() { /* ... */ }
    override val x: Int get() = 0
    
    inner class Example {
        fun ex() {
            super@Sub.f() 
            println(super@Sub.x) 
        }
    }
}
```
As a final note, all classes in Kotlin have a common superclass "Any", that is the default superclass for a class with no supertypes declared.
#### Go

    
### Reflection
#### What reflection abilities are supported?
##### Kotlin
Kotlin allows for the use of reflection to see what type, class, properties, and functions an object possesses. It also allows for the referencing of constructors.
##### Go

#### How is reflection used?
##### Kotlin
Below are a few examples of Kotlin's reflection syntax:
```kotlin
val c = Example::class //here we are grabbing the class of Example

fun isOdd(x: Int) = x % 2 != 0 //here reflection is used to grab reference to a function
val numbers = listOf(1, 2, 3)
println(numbers.filter(::isOdd))

val x = 1 //here we use reflection to get the property x
fun main(args: Array<String>) {
    println(::x.get())
    println(::x.name) 
}
```
##### Go

    
### Memory management
#### How is it handled?
##### Kotlin
With Kotlin (much like Java), all objects are placed onto a heap divided into two spaces. Once full, garbage collection scans through the heap.
##### Go

#### How does it work?
##### Kotlin
The first of said spaces is the nursery, which holds younger objects and causes garbage collection to run once full. If an object is "old" enough it will be moved into the second space, i.e. the old space, by the garbage collector instead of being destroyed. If the old space hits capacity the garbage collector will run on it, destroying objects that are not being used.
##### Go

#### Garbage collection?
##### Kotlin
As mentioned above, Kotlin does take advantage of garbage collection.
##### Go

#### Automatic reference counting?
##### Kotlin
Kotlin does not have automatic reference counting. Its use of garbage collection makes such a feature unneeded. 
##### Go

   
### Comparisons of references and values
#### How are values compared? (i.e. comparing two strings)
##### Kotlin
Kotlin uses == and != for comparison. They reference structual integrity, with == being functionally equivilent to Java's .equals() method. So, it works for strings as well.
```kotlin
    x == y
    // is equivalent to
    x?.equals(y) ?: (y === null)
```
As for referential equality, Kotlin uses === and !== to check if references are pointing to the same object. 
##### Go

    
### Null/nil references
#### Which does the language use? (null/nil/etc)
##### Kotlin
Kotlin uses "null" for empty objects and null pointers. 
##### Go

#### Does the language have features for handling null/nil references?
##### Kotlin
Many of Kotlin's features were created with prevnting danger that could occur from null references in mind. This includes the fact that both variables and collections can be "nullable" by placing a ? after the type. This means they are allowed to hold null values. If a non-nullable variable is set to null, it will cause a compilation error. In addition, Kotlin has "Null Safety" as mentioned in the Unique Features section. To reiterate, by using its simple ? operator, it first checks the value to see if it is null or not. If it’s not null then only then it will perform the next operation. It is used as shown. 
```kotlin
val str:String? = "name"
``` 
As a last note, Kotlin has access to the NullPointerException for error handling in regard to null values.
##### Go

    
### Errors and exception handling
##### Kotlin

##### Go

    
### Lambda expressions, closures, or functions as types
##### Kotlin

##### Go

    
### Implementation of listeners and event handlers
##### Kotlin

##### Go

    
### Singleton
#### How is a singleton implemented?
##### Kotlin

##### Go

#### Can it be made thread-safe?
##### Kotlin

##### Go

#### Can the singleton instance be lazily instantiated?
##### Kotlin

##### Go

    
### Procedural programming
#### Does the language support procedural programming?
##### Kotlin
Kotlin supports procedural programming. So, functions and variables can be defined without placing them explicitly in classes. 
##### Go


### Functional programming
#### Does the language support functional programming?
##### Kotlin
Kotlin supports functional programming. It allows for the use of both OO and FP styles, or mixed elements of the two. The FP styles include, but are not limited too, higher-order functions, function types, and lambdas.
##### Go

    
### Multithreading
#### Threads or thread-like abilities
##### Kotlin

##### Go

#### How is multitasking accomplished?
##### Kotlin

##### Go



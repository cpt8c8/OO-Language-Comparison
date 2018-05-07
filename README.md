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
JetBrains was looking for a language that adresses their needs, had fast compile times, was streamlined, and could ineract with a replace Java.
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

##### Go

#### How are name spaces used?
##### Kotlin

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
You can also have custom setterans and getters if you would like.
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

##### Go

#### What abilities does it have?
##### Kotlin

##### Go

#### How is it used?
##### Kotlin

##### Go

### Inheritance / extension
#### Kotlin

#### Go

    
### Reflection
#### What reflection abilities are supported?
##### Kotlin

##### Go

#### How is reflection used?
##### Kotlin

##### Go

    
### Memory management
#### How is it handled?
##### Kotlin

##### Go

#### How does it work?
##### Kotlin

##### Go

#### Garbage collection?
##### Kotlin

##### Go

#### Automatic reference counting?
##### Kotlin

##### Go

   
### Comparisons of references and values
#### How are values compared? (i.e. comparing two strings)
##### Kotlin

##### Go

    
### Null/nil references
#### Which does the language use? (null/nil/etc)
##### Kotlin

##### Go

#### Does the language have features for handling null/nil references?
##### Kotlin

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

##### Go


### Functional programming
#### Does the language support functional programming?
##### Kotlin

##### Go

    
### Multithreading
#### Threads or thread-like abilities
##### Kotlin

##### Go

#### How is multitasking accomplished?
##### Kotlin

##### Go



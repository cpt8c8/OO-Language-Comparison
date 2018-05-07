# OO-Language-Comparison
## Kotlin Vs. Python
## Samantha Trenholm and Matt Tschannen

### Language purpose/genesis
#### Why was the language created?
##### Kotlin
Kotlin was developed by JetBrains primarily for internal use. It was intended to boost productivty and improve workflow, which would result in improved sales.
##### Python
Python was created as a pet project by Guido van Rossum, originally intended to be a scripting language that took ideas from an earlier general purpose called ABC.

#### What problems was the language trying to address?
##### Kotlin
JetBrains was looking for a language that adresses their needs, had fast compile times, was streamlined, and could ineract with and replace Java.
##### Python
Python was created with the goals of being extremely readable and high level, and being very extensible, allowing it to have lots of inherent multi-paradigm support and making it easy to add even more programming paradigms beyond what is included in the vanilla distribution.

#### Is the language a reaction to a previous language or a replacement for another language?
##### Kotlin
It was largely intended, as mentioned above, to be a replacement for Java.
##### Python
Python was a reaction to essentially the entire ecosystem of lower-level, abstract languages. It brought object oriented, functional and other concepts into one package that emphasized readability and simplicity

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
##### Python
The truly unique thing about python is its simplicity, syntax is unobtrustive. Available libraries are also exaustive in their coverage of many basic and more complex. These two characteristics mean that you can accomplish a lot with fewer characters and lines of code than previous languages. Below is in example of this, note that these two code snippets do the exact same thing but the python code looks much cleaner
###### Python
```python
data = Series(['A','B','C','D','E','F'], index = [0,2,5,7,12,14])
data.reindex(range(14),method='ffill')
```
###### C
```c
char array1[6][2] = {{'A','0'},{'B','2'},{'C','5'},{'D','7'},{'E','12'},{'F','14'}};
char array2[14];
int hold = 0;
int arrayidx = 0;

for(int i = 0; i < 14; i++){
	if(atoi(array1[arrayidx][1]) == i){
		array2[i] = array1[arrayidx][0];
		hold = array1[arrayidx][0];
		arrayidx++;
	}
	else{
		array2[i] = hold;
	}
}
```

### Name spaces
#### How are name spaces implemented? 
##### Kotlin
Kotlin follows Java's naming conventions. Names of packages are always lower case and do not use underscores, names of classes and objects start with an upper case letter and use camel humps, names of functions, properties and local variables start with a lower case letter and use camel humps and no underscores (with the exception of factory functions used to create instances of classes, which can have the same name as the class being created), and names for tests (and only tests) can have method names with spaces enclosed in backticks. The naming conventions for properties are as follows: names of constants should use uppercase underscore-separated names, names of top-level or object properties which hold objects with behavior or mutable data should use regular camel-hump names, names of properties holding references to singleton objects can use the same naming style as object declarations, and for enum constants, it's OK to use either uppercase underscore-separated names (enum class Color { RED, GREEN }) or regular camel-humps names starting with an uppercase letter, depending on the usage.
##### Python

#### How are name spaces used?
##### Kotlin
Kotlin's namespaces are implemented very similarly to Java. The package is described at the top of the document with imports (typically) below it, as such.
```kotlin
package foo.bar
import foo.*
```
##### Python

    
### Types
#### What types does the language support?
##### Kotlin
Kotlin can represent numbers through the types Byte, Short, Int, Long, Float, and Double. It also supports Char, String, and Boolean. 
##### Python

#### Are both reference and value types supported?
##### Kotlin
Kotlin supports both reference and value tyoes.
##### Python

#### Can new value types be created?
##### Kotlin
Kotlin does not facilitate the creation of basic types.
##### Python
   
### Classes
#### Defining
##### Kotlin
Classes are easily defined in Kotlin, as show below.
```kotlin
class Example {
    // ...
}
```
##### Python

#### Creating new instances
##### Kotlin
A instance of a Class can be created as shown below.
```kotlin
val ex = Example()
//or
val exXx = ExXxample("Like that Vin Diesal movie")
```
##### Python

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
##### Python

#### Destructing/de-initializing
##### Kotlin
Objects in Kotlin can be destructured into multiple values.
```kotlin
val (variableOne, variableTwo) = example 
```
This leaves us with two newly declared variables.
##### Python

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
##### Python

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
##### Python

#### Backing variables?
##### Kotlin
In Kotlin you have backing fields, which help you refer to the property inside the getter and setter methods. You must use them becuase using the property directly inside the getter or setter causes a recursive call which will generate a StackOverflowError. The Kotlin code in the getters and setters example has these in use (the fields have been named "field" for ease of identification). 
##### Python

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
##### Python

    
### Interfaces / protocols
#### What does the language support?
##### Kotlin
Kotlin does support interfaces, and they are implemented very similarly to Java 8. A class can implement many interfaces.
##### Python

#### What abilities does it have?
##### Kotlin
Kotlin interfaces can contain declarations of abstract methods and method implementations. However, they cannot store state. They can have properties as long as they are abstract or provide accessor implementations.
##### Python

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
##### Python

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
#### Python

    
### Reflection
#### What reflection abilities are supported?
##### Kotlin
Kotlin allows for the use of reflection to see what type, class, properties, and functions an object possesses. It also allows for the referencing of constructors.
##### Python

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
##### Python

    
### Memory management
#### How is it handled?
##### Kotlin
With Kotlin (much like Java), all objects are placed onto a heap divided into two spaces. Once full, garbage collection scans through the heap.
##### Python

#### How does it work?
##### Kotlin
The first of said spaces is the nursery, which holds younger objects and causes garbage collection to run once full. If an object is "old" enough it will be moved into the second space, i.e. the old space, by the garbage collector instead of being destroyed. If the old space hits capacity the garbage collector will run on it, destroying objects that are not being used.
##### Python

#### Garbage collection?
##### Kotlin
As mentioned above, Kotlin does take advantage of garbage collection.
##### Python

#### Automatic reference counting?
##### Kotlin
Kotlin does not have automatic reference counting. Its use of garbage collection makes such a feature unneeded. 
##### Python

   
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
##### Python

    
### Null/nil references
#### Which does the language use? (null/nil/etc)
##### Kotlin
Kotlin uses "null" for empty objects and null pointers. 
##### Python

#### Does the language have features for handling null/nil references?
##### Kotlin
Many of Kotlin's features were created with prevnting danger that could occur from null references in mind. This includes the fact that both variables and collections can be "nullable" by placing a ? after the type. This means they are allowed to hold null values. If a non-nullable variable is set to null, it will cause a compilation error. In addition, Kotlin has "Null Safety" as mentioned in the Unique Features section. To reiterate, by using its simple ? operator, it first checks the value to see if it is null or not. If it’s not null then only then it will perform the next operation. It is used as shown. 
```kotlin
val str:String? = "name"
``` 
As a last note, Kotlin has access to the NullPointerException for error handling in regard to null values.
##### Python

    
### Errors and exception handling
##### Kotlin
In Kotlin, exceptions can be thrown with the 'throw' keyword and uses try and catch statements very similarly to Java. 
```kotlin
    try {
        //...
    }
    catch (e: AThrownException) {
        //...
    }
```
Kotlin, more uniquely, also allows try functions to return values. In addition, is has the "Nothing" keyword, which labels code as "a value that never exists." This meaning that the function will never return anything, only throw exceptions. 
```kotlin
 fun woops(except: String): Nothing {
        throw IllegalArgumentException(except)
    }

    val x = obj.input ?: woops("invalid input")
    println(x)
```
##### Python

    
### Lambda expressions, closures, or functions as types
##### Kotlin
Kotlin denotes its functions as "First Class", meaning that they can be stored in variables and data structures. In addition, they can be passed to or returned from higher order functions. On top of that, Kotlin has lambda expressions. The syntax is as shown,
```kotlin
val example = { x: Int, y: Int -> x + y }
//example = object holding function
//x, y = arguments passed to function
```
##### Python

    
### Implementation of listeners and event handlers
##### Kotlin
Kotlin has a very streamlined implemtation of listeners and event handlers. Its ability to use lambda expressions and pass them as arguments helps to make the listener/handler statements very concise. 
```kotlin
fun setOnClickListener(listener: (View) -> Unit)
button.setOnClickListener({ view -> doSomething() })
```
##### Python

    
### Singleton
#### How is a singleton implemented?
##### Kotlin
In Kotlin, singletons are implemented as objects. So, you do not have to create a class for them. Creating one is extremely simple.
```kotlin
object Singleton {
    init {
        //...
    }
}
```
##### Python

#### Can it be made thread-safe?
##### Kotlin
Singletons can be made thread safe in Kotlin.
##### Python

#### Can the singleton instance be lazily instantiated?
##### Kotlin
In Kotlin, singletons can be lazily instantiated after it is first accessed. 
##### Python

    
### Procedural programming
#### Does the language support procedural programming?
##### Kotlin
Kotlin supports procedural programming. So, functions and variables can be defined without placing them explicitly in classes. 
##### Python


### Functional programming
#### Does the language support functional programming?
##### Kotlin
Kotlin supports functional programming. It allows for the use of both OO and FP styles, or mixed elements of the two. The FP styles include, but are not limited too, higher-order functions, function types, and lambdas.
##### Python

    
### Multithreading
#### Threads or thread-like abilities
##### Kotlin
Kotlin supports the use of both threads and coroutines.
##### Python

#### How is multitasking accomplished?
##### Kotlin
In Kotlin, you can create threads either by extending the Thread class or implementing the Runnable interface. 
```kotlin
    class ExtendThread: Thread() {
        public override fun run() {
            //...
        }
    }
    class ImplementRunnable: Runnable {
        public override fun run() {
            //...
        }
    }
```
Either way, the thread must be started by calling start() in main. 
I also mentioned that Kotlin supports coroutines. That is actually only partially true, as currently coroutines are only experimental in Kotlin. A coroutine is a computation that can be suspended without blocking a thread. Blocking threads is fairly expensive, so coroutines exist as a method that is less expensive to suspend. That being said, coroutines are only suspendable at specific points. For a coroutine to be blocked, a suspend call must be declared with "suspend" before "fun".
##### Python



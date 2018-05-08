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
The truly unique thing about python is its simplicity, syntax is unobtrustive. Available libraries are also exaustive in their coverage of many basic and more complex. These two characteristics mean that you can accomplish a lot with fewer characters and lines of code than previous languages. Below is in example of this, note that these two code snippets have the same logical input and output.
###### Python
```python
data = Series(['A','B','C','D','E','F'], index = [0,2,5,7,12,14])
data.reindex(range(14),method='ffill')
```
###### C
```c
char array1[6][2] = {{'A','0'},{'B','2'},{'C','5'},{'D','7'},{'E','12'},{'F','14'}};
char data[14];
int hold = 0;
int arrayidx = 0;

for(int i = 0; i < 14; i++){
	if(atoi(array1[arrayidx][1]) == i){
		data[i] = array1[arrayidx][0];
		hold = array1[arrayidx][0];
		arrayidx++;
	}
	else{
		data[i] = hold;
	}
}
```

### Name spaces
#### How are name spaces implemented? 
##### Kotlin
Kotlin follows Java's naming conventions. Names of packages are always lower case and do not use underscores, names of classes and objects start with an upper case letter and use camel humps, names of functions, properties and local variables start with a lower case letter and use camel humps and no underscores (with the exception of factory functions used to create instances of classes, which can have the same name as the class being created), and names for tests (and only tests) can have method names with spaces enclosed in backticks. The naming conventions for properties are as follows: names of constants should use uppercase underscore-separated names, names of top-level or object properties which hold objects with behavior or mutable data should use regular camel-hump names, names of properties holding references to singleton objects can use the same naming style as object declarations, and for enum constants, it's OK to use either uppercase underscore-separated names (enum class Color { RED, GREEN }) or regular camel-humps names starting with an uppercase letter, depending on the usage.
##### Python
Namespaces are implemented in python as dictionaries, with names being dictionary keys that map to their represented objects. Some namepaces in python include the global scope of a python module(package), the local scope of a method or function, and built in names like standard functions; abs(), cmp(), ...
#### How are name spaces used?
##### Kotlin
Kotlin's namespaces are implemented very similarly to Java. The package is described at the top of the document with imports (typically) below it, as such.
```kotlin
package foo.bar
import foo.*
```
##### Python
namespaces can be created by declaring package names that can then be pulled in using "import" keyword. Subpackages can also be imported without taking the whole package, any functions that are called must be referenced from the subpackage name unless the "as" keyword is used, which allows you to cast a package object to a different name.
```python
from fibo import fib as fibonacci
fibonacci(500)
```
    
### Types
#### What types does the language support?
##### Kotlin
Kotlin can represent numbers through the types Byte, Short, Int, Long, Float, and Double. It also supports Char, String, and Boolean. 
##### Python
Python supports int, float and complex num types, list, tuple and range sequence types, a string type, a mapping type(dict), binary types and others.

#### Are both reference and value types supported?
##### Kotlin
Kotlin supports both reference and value tyoes.
##### Python
Yes, but in an unusual way, all variables in python are essentially reference types, but they can behave like either a reference or a value type. 
#### Can new value types be created?
##### Kotlin
Kotlin does not facilitate the creation of basic types.
##### Python
Yes, creating new value types is supported in python.
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
Classes are very simple to define in python, refer to the code below for syntax.
```python
class MyClass:
    a = 1
    b = "Hello"
```

#### Creating new instances
##### Kotlin
A instance of a Class can be created as shown below.
```kotlin
val ex = Example()
//or
val exXx = ExXxample("Like that Vin Diesal movie")
```
##### Python
A instance of a python Class can be created as shown below.
```python
classVariable = MyClass()
```

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
Contstructors can be declared in a class by defining a method called "\_\_init\_\_()" within the class scope.
```python
class Point(object):
    def __init__(self,x = 0,y = 0):
        self.x = x
        self.y = y
```


#### Destructing/de-initializing
##### Kotlin
Objects in Kotlin can be destructured into multiple values.
```kotlin
val (variableOne, variableTwo) = example 
```
This leaves us with two newly declared variables.
##### Python
Certain objects such as dictionaries can be destructured, but there is not an elegant way to destrcture custom objects.

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
Python uses the "self" keyword to make reference to the containing object, see code example below for how it may be used in a constructor.
```python
class Point(object):
    def __init__(self,x = 0,y = 0):
        self.x = x
        self.y = y
```

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
Getters and setters must be built by the user, they are not inherent to python classes/

#### Backing variables?
##### Kotlin
In Kotlin you have backing fields, which help you refer to the property inside the getter and setter methods. You must use them becuase using the property directly inside the getter or setter causes a recursive call which will generate a StackOverflowError. The Kotlin code in the getters and setters example has these in use (the fields have been named "field" for ease of identification). 
##### Python
In python, backing variables are usually denoted by an underscore preceding the variable name(\_varibalename)

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
Python supports computed attributes, which are attributes that look like a variable but call a function whenever the attribute is referenced.
    
### Interfaces / protocols
#### What does the language support?
##### Kotlin
Kotlin does support interfaces, and they are implemented very similarly to Java 8. A class can implement many interfaces.
##### Python
Python supports interfaces, and their implementation is very similar to java.

#### What abilities does it have?
##### Kotlin
Kotlin interfaces can contain declarations of abstract methods and method implementations. However, they cannot store state. They can have properties as long as they are abstract or provide accessor implementations.
##### Python
Interfaces can declare abstract methods but cannot store information or declare attributes.

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
Below is an example implementation of a python interface.
```python
class IInterface(object):
    def __init__(self):
        pass

    def show(self):
        raise Exception("NotImplementedException")


class MyClass(IInterface):
   def __init__(self):
       IInterface.__init__(self)

   def show(self):
       print 'Hello World!'
```

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
Python supports both singular and multiple inheritence, below is a code example.
```python
class Person:

    def __init__(self, first, last):
        self.firstname = first
        self.lastname = last

    def __str__(self):
        return self.firstname + " " + self.lastname

class Employee(Person):

    def __init__(self, first, last, staffnum):
        super().__init__(first, last)
        self.staffnumber = staffnum
```
    
### Reflection
#### What reflection abilities are supported?
##### Kotlin
Kotlin allows for the use of reflection to see what type, class, properties, and functions an object possesses. It also allows for the referencing of constructors.
##### Python
Python provides the ability to examine the type and attributes of objects with simple library functions.

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
Below is an example of how you can retrieve the type of an object.
```python
	type(3) is int #returns true

```

    
### Memory management
#### How is it handled?
##### Kotlin
With Kotlin (much like Java), all objects are placed onto a heap divided into two spaces. Once full, garbage collection scans through the heap.
##### Python
Python has automatic memory management which utilizes dynamic typing and a combination of reference counting and cycle-detecting garbage collection.

#### How does it work?
##### Kotlin
The first of said spaces is the nursery, which holds younger objects and causes garbage collection to run once full. If an object is "old" enough it will be moved into the second space, i.e. the old space, by the garbage collector instead of being destroyed. If the old space hits capacity the garbage collector will run on it, destroying objects that are not being used.
##### Python
Like many modern languages, python uses automatic garbage collection, which periodically scans through memory looking for unused variables, and clearing them out accordingly.

#### Garbage collection?
##### Kotlin
As mentioned above, Kotlin does take advantage of garbage collection.
##### Python
Yes, python implements garbage collection features.

#### Automatic reference counting?
##### Kotlin
Kotlin does not have automatic reference counting. Its use of garbage collection makes such a feature unneeded. 
##### Python
Yes, python implements reference counting features.

   
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
Python uses == and != for string comparison, "in" and "not in" operators are also available for checking to see whether or not a sub string is contained within a superstring. 
    
### Null/nil references
#### Which does the language use? (null/nil/etc)
##### Kotlin
Kotlin uses "null" for empty objects and null pointers. 
##### Python
In python, the null equivalent is the "None" singleton, which denotes an empty object.

#### Does the language have features for handling null/nil references?
##### Kotlin
Many of Kotlin's features were created with prevnting danger that could occur from null references in mind. This includes the fact that both variables and collections can be "nullable" by placing a ? after the type. This means they are allowed to hold null values. If a non-nullable variable is set to null, it will cause a compilation error. In addition, Kotlin has "Null Safety" as mentioned in the Unique Features section. To reiterate, by using its simple ? operator, it first checks the value to see if it is null or not. If it’s not null then only then it will perform the next operation. It is used as shown. 
```kotlin
val str:String? = "name"
``` 
As a last note, Kotlin has access to the NullPointerException for error handling in regard to null values.
##### Python
Yes, generally None references are handled by throwing a TypeError exception, see code below.
```python
    if object is None:
    	raise TypeError
```

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
The implementation of exception handling in python is pretty simple, first you declare a try statement, and for failures you can declare one or more except cases to give you more detailed info on the type of exception.
```python
    try:
    	x = int(input("Please enter a number: "))
    	break

    except ValueError:
    	print("Oops!  That was no valid number.  Try again...")
```
 
### Lambda expressions, closures, or functions as types
##### Kotlin
Kotlin denotes its functions as "First Class", meaning that they can be stored in variables and data structures. In addition, they can be passed to or returned from higher order functions. On top of that, Kotlin has lambda expressions. The syntax is as shown,
```kotlin
val example = { x: Int, y: Int -> x + y }
//example = object holding function
//x, y = arguments passed to function
```
##### Python
Lambda functions are fairly simple to implement in python, keeping in line with its functional programming roots.
```python
    f = lambda x, y : x + y
    f(1,1)
```

    
### Implementation of listeners and event handlers
##### Kotlin
Kotlin has a very streamlined implemtation of listeners and event handlers. Its ability to use lambda expressions and pass them as arguments helps to make the listener/handler statements very concise. 
```kotlin
fun setOnClickListener(listener: (View) -> Unit)
button.setOnClickListener({ view -> doSomething() })
```
##### Python
Python doesnt support prebuilt event listeners, but there is a python Event class which can be used to signal events across threads with the setting and unsetting of flags, so checking for events has to be a somewhat manual process, where flag checks are done only when requested.
    
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
Singletons are not commonly used in python, perhaps because they are cumbersome to implement, here's a code example of how one can be implemented.
```python
    class Singleton:
    __instance = None

    @staticmethod
    def getInstance():
        if Singleton.__instance == None:
            Singleton()
        return Singleton.__instance 

    def __init__(self):
        if Singleton.__instance != None:
            raise Exception("This class is a singleton!")
        else:
            Singleton.__instance = self
```

#### Can it be made thread-safe?
##### Kotlin
Singletons can be made thread safe in Kotlin.
##### Python
Yes, singletons can be made thread safe in python.

#### Can the singleton instance be lazily instantiated?
##### Kotlin
In Kotlin, singletons can be lazily instantiated after it is first accessed. 
##### Python
Yes, lazy instatiation is possible for with python singletons.

    
### Procedural programming
#### Does the language support procedural programming?
##### Kotlin
Kotlin supports procedural programming. So, functions and variables can be defined without placing them explicitly in classes. 
##### Python
Python supports procedural programming concepts.


### Functional programming
#### Does the language support functional programming?
##### Kotlin
Kotlin supports functional programming. It allows for the use of both OO and FP styles, or mixed elements of the two. The FP styles include, but are not limited too, higher-order functions, function types, and lambdas.
##### Python
Python supports functional programming concepts, and includes some standard functions common to functional programming(filter(), map(), reduce())
    
### Multithreading
#### Threads or thread-like abilities
##### Kotlin
Kotlin supports the use of both threads and coroutines.
##### Python
Python supports threading and coroutines.

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
Creating new threads in Python is fairly simple. All you have to do is write the function you'd like to thread, and pass it to the start_new_thread() function of the thread library, along with any optional arguments contained in a tuple.
```python
    thread.start_new_thread(function(), args)
```



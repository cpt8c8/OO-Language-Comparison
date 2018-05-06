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

```val str:String? = "name"```

Other things of note include that Kotlin is completely inter-operable with Java, its ability to return multiple values, and the ability to have default and named arguments (as shown below).
```
fun example(num: Int, str: String = "9") {}

example(15, "Hey")

example(str = "Name", num = 45) //Named argument

example(45) //usage of default argument
```
##### Go
One interesting feature of go is its concurrency features, namely the use of goroutines and channels. These features allow for code to be optimized for parallelism and asynchrony with ease. Any function can be called as a goroutine in Go, and Go will automatically handle whether or not a new thread should be started or if it would be more efficient to execute the operation on an existing thread. This minimizes excessive Thread creation which can actually slow down your program,  because despite the advantages of parallel processing thread creation is a fairly expensive task. To allow for these go routines to exchange information asynchronously, Go supports the use of channels which provide a FIFO storage entity that goroutines can use to drop off and pick up information when they are ready to do so.

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

##### Go
Go supports several basic int, float and string types, as well as derived types. Many more types are available through the go/types library and others. 

#### Are both reference and value types supported?
##### Kotlin

##### Go
Reference and value types are both supported, keeping in line with Go’s C heritage.

#### Can new value types be created?
##### Kotlin

##### Go
New concrete types can certainly be created through structs, but there isn’t support to create additional basic types.
    
### Classes
#### Defining
##### Kotlin

##### Go

#### Creating new instances
##### Kotlin

##### Go

#### Constructing/initializing
##### Kotlin

##### Go

#### Destructing/de-initializing
##### Kotlin

##### Go

#### Instance reference name in data type (class)
        this? self?
##### Kotlin

##### Go

    
### Properties
#### Getters and setters…write your own or built in?
##### Kotlin

##### Go

#### Backing variables?
##### Kotlin

##### Go

#### Computed properties?
##### Kotlin

##### Go

    
### Interfaces / protocols
#### What does the language support?
##### Kotlin

##### Go

#### What abilities does it have?
##### Kotlin

##### Go

#### How is it used?

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



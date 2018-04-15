# Java

## Language purpose/genesis

### Why was the language created?

Java was originally created to work for interactive television. However, it was too advanced 
for this at the time, and its dynamic was changed to work more universally across various systems.
Essentially the code was to be written once and used everywhere. 

### What problems was the language trying to address?

It was created with five different goals it was attempting to achieve in order to be superior to 
previous languages. These goals were: 
* Simplicity, Object Oriented and Familiar
* Robust and Secure --> addressing reliability and security concerns
* Architecture Neutral and Portable --> addresses execution of programs on any OS or environment.  
* High Performance --> addresses performance issues
* Interpreted, Threaded, and Dynamic --> addresses heavy compilation, concurrency, and linking issues

### Is the language a reaction to a previous language or a replacement for another language?
It was developed as somewhat of a replacement for C++. It was to do everything that C++ did while 
removing the hassle of lower level tasks such as memory management. 

## Unique features of the language

### Does the language have any particularly unique features?
Not particularly. The main thing is that it is Platform Indepedent/Architecture Neutral, which is 
fairly rare for languages. 

## Name spaces 
### How are name spaces implemented?
They are called packages in Java and must be at the top of a Java file as follows: 
```java 
  package HelloWorld; 
  
  class Hello {
    //Code here
  }
```
### How are name spaces used?
They are used to organize files and avoid class conflicts. 

## Types

* What types does the language support?

There are 8 primitive data types supported by java. They are: 
```java
byte
short
int
long
float
double
boolean
char
```
It also supports reference types such as classes, interfaces, and arrays.

* Are both reference and value types supported?

Yes

* Can new value types be created?

No, only reference types. Java does not have structs.

## Classes

* Defining

A new class is defined as follows: 
```java 
  class MyClass {
      //Code in the class
  }
```

* Creating new instances

An instance of a class is created as follows: 
```java 
  class MyClass {
      //Instantiation of class named NewClass with default constructor
      NewClass class = new NewClass();
  } 
```

* Constructing/initializing

```java 
  class MyClass {
      
      MyClass() {
          //Default constructor
      }
      
      MyClass(Type field) {
          //Constructor with a parameter
      }    
  }
```

* Destructing/de-initializing

```java 
  class MyClass {
      
     protected void finalize() throws Throwable {
        // Invoke the finalizer of the superclass
        super.finalize();
        //other code to handle files etc
     }
  }
```

Instance reference name in data type (class)

* this? self?
Properties

* Getters and setters…write your own or built in?
* Backing variables?
* Computed properties?

Interfaces / protocols

* What does the language support?
* What abilities does it have?
* How is it used?

Inheritance / extension

Reflection

* What reflection abilities are supported?
* How is reflection used?

Memory management

* How is it handled?
* How does it work?
* Garbage collection?
* Automatic reference counting?

Comparisons of references and values

* How are values compared? (i.e. comparing two strings)

Null/nil references

* Which does the language use? (null/nil/etc)
* Does the language have features for handling null/nil references?

Errors and exception handling

Lambda expressions, closures, or functions as types

Implementation of listeners and event handlers

Singleton

* How is a singleton implemented?
* Can it be made thread-safe?
* Can the singleton instance be lazily instantiated?

Procedural programming

* Does the language support procedural programming?

Functional programming

* Does the language support functional programming?

Multithreading

* Threads or thread-like abilities
* How is multitasking accomplished?

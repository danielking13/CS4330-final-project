# Java

## Language purpose/genesis

#### Why was the language created?

Java was originally created to work for interactive television. However, it was too advanced
for this at the time, and its dynamic was changed to work more universally across various systems.
Essentially the code was to be written once and used everywhere.

#### What problems was the language trying to address?

It was created with five different goals it was attempting to achieve in order to be superior to
previous languages. These goals were:
* Simplicity, Object Oriented and Familiar
* Robust and Secure --> addressing reliability and security concerns
* Architecture Neutral and Portable --> addresses execution of programs on any OS or environment.  
* High Performance --> addresses performance issues
* Interpreted, Threaded, and Dynamic --> addresses heavy compilation, concurrency, and linking issues

#### Is the language a reaction to a previous language or a replacement for another language?
It was developed as somewhat of a replacement for C++. It was to do everything that C++ did while
removing the hassle of lower level tasks such as memory management.

## Unique features of the language

#### Does the language have any particularly unique features?
Not particularly. The main thing is that it is Platform Indepedent/Architecture Neutral, which is
fairly rare for languages.

## Name spaces
#### How are name spaces implemented?
They are called packages in Java and must be at the top of a Java file as follows:
```java
  package HelloWorld;

  class Hello {
    //Code here
  }
```
#### How are name spaces used?
They are used to organize files and avoid class conflicts.

## Types

#### What types does the language support?
Primitive Types
* byte
* short
* int
* long
* float
* double
* boolean
* char

Reference Types
* Objects
* Classes
* Interfaces
* Arrays

#### Are both reference and value types supported?
Yes

#### Can new value types be created?
No, only reference types. Java does not have structs.

## Classes

#### Defining
A new class is defined as follows:
```java
  class MyClass {
      //Code in the class
  }
```

#### Creating new instances
An instance of a class is created as follows:
```java
  class MyClass {
      //Instantiation of class named NewClass with default constructor
      NewClass class = new NewClass();
  }
```

#### Constructing/initializing

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

#### Destructing/de-initializing

```java
  class MyClass {

     protected void finalize() throws Throwable {
        // Invoke the finalizer of the superclass
        super.finalize();
        //other code to handle files etc
     }
  }
```

## Instance reference name in data type (class)
#### this? self?
Java uses this to refer to a class data type as follows:
```java
public class Employee {
    public Employee(string name, string alias) {
      // Use this to qualify the fields, name and alias:
      this.name = name;
      this.alias = alias;
    }
}
```

## Properties
#### Getters and setters…write your own or built in?
```java
public class Data {
    private int month = 7; //backing variable

    public int getMonth() {
      return month;
    }
    public void setMonth(int month) {
      if ((month > 0) && (month < 13)) {
      this.month = month;
      }
    }
}
```

#### Backing variables?
Java does not have backing variables.   
#### Computed properties?
Yes, through the use of a custom getter as follows:
```java
public class Person {
    private int age;
    private int yearOfBirth;

    //like a computed property
    public int getAge() {
      return 2018 - yearOfBirth; // would use Java time here normally
    }
    public void setAge(int age) {
      this.age = age;
    }
}
```

Interfaces / protocols

#### What does the language support?
Interfaces
#### What abilities does it have?
It is used to achieve abstraction, to support multiple inheritance, and to
achieve loose coupling. It contains only abstract methods and public, static,
final fields.
#### How is it used?
```java
interface SampleInterface {
    void sampleMethod();
}

class ImplementationClass implements SampleInterface {
    @Override
    void sampleMethod() {
        // Method implementation.
    }

    public static void main(String args[]) {
        // Declare an interface instance.
        SampleInterface obj = new ImplementationClass();

        // Call the member.
        obj.sampleMethod();
    }
}
```
## Inheritance / extension

In Java, inheritance is supported. To inherit you use the ```extends``` keyword..

```java
class Sparrow extends Bird {
   // fields and methods of sparrow
}
```

## Reflection

#### What reflection abilities are supported?

The required classes for reflection are in the java.lang.reflect package. Relfection can be used to get the following information:


#### How is reflection used?

## Memory management

* How is it handled?

Memory allocated on the heap is managed automatically.

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

## Implementation of listeners and event handlers

Java has an ```java EventListener ```. The EventListener is a tagging interface that all event listener interfaces must extend. For example, the MouseListener. An EventListener is an object that implements an interface for event handling.

```java
public class MyClass
{
    Button myButton;

    MyClass()
    {
        ...
        myButton.addMouseListener(new ButtonHandler());
    }

    public class ButtonHandler implements MouseListener
    {
        public void mousePressed(MouseEvent e) {}
        public void mouseReleased(MouseEvent e) {}
        public void mouseEntered(MouseEvent e) {}
        public void mouseExited(MouseEvent e) {}

        public void mouseClicked(MouseEvent e)
        {
           doSomething("Mouse clicked", e);
        }
    }
}
```

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

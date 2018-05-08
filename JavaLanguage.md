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
Not particularly. The main thing is that it is Platform Independent/Architecture Neutral, which is
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
Java does not have an explicit destructor; however, it does have a method that
can be used sparingly to help clean up the object. It is not very reliable,
but can be used in a worst case scenario as follows:
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
Java uses ```this``` to refer to a class data type as follows:
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
Write your own as seen below:
```java
public class Data {
    private int month = 7;

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

## Interfaces / protocols

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
The required classes for reflection are in the java.lang.reflect package.
Reflection can be used to get the following information:

| Information  | About  |
|---|---|
|  Class   | The getClass() method is used to get the name of the class to which an object belongs.  |
|  Constructors |  The getConstructors() method is used to get the public constructors of the class to which an object belongs. |
| Methods | The getMethods() method is used to get the public methods of the class to which an objects belongs. |
|  Parameters  | getDeclaredMethod() : To create an object of method to be invoked. |
| Fields  | getDeclaredMethod() : To create an object of method to be invoked. |

#### How is reflection used?

Reflection is used to get information about the class to which an object belongs. It also gives information about the methods of a class. Through reflection we can invoke methods at runtime irrespective of the access specifier used with them.

## Memory management

#### How is it handled?

Memory allocated on the heap is managed automatically. The heap is created when the JVM starts and increases or decreases in size while an application runs.

#### How does it work?

A heap is divided into two areas (generations) called the nursery (young) and old space. The nursery is for new objects. If the nursery becomes full then there is a special, 'young collection' that is run. If an object has lived long enough then it is promoted to the old space. If the old space becomes full then there is a process of 'old collection'.

#### Garbage collection?

When the heap becomes full, the garbage is collected. During the garbage collection objects that are no longer used are cleared, thus making space for new objects.

#### Automatic reference counting?

There is no automatic reference counting in Java. The garbage collector does the reference management for you.

## Comparisons of references and values

#### How are values compared? (i.e. comparing two strings)

| Comparison  | About  |
|---|---|
|  a == b, a != b  | Compares two references -- not values. This is used to compare to see if a reference is null, to compare two enum values, or to check if they are the same object|
|  a.equals(b) |  This compares to object values for equality i.e. the same value. |
| a.compareTo(b) | Returns an int and tells if the values compared are less than, equal, or greater than.  |


## Null/nil references

#### Which does the language use? (null/nil/etc)

Java uses ```null```.

#### Does the language have features for handling null/nil references?

Java has the NullPointerException to handle an object reference that has a null value. It is a RuntimeException. A NullPointerException can occur:

* Invoking a method from a null object.
* Accessing or modifying a null object’s field.
* Taking the length of null, as if it were an array.
* Accessing or modifying the slots of null object, as if it were an array.
* Throwing null, as if it were a Throwable value.
* When you try to synchronize over a null object.

## Errors and exception handling

All exceptions are subtypes of ```java.lang.Exception``` class.
This class is a subclass of the ```Throwable``` class.
There is another subclass called ```Error``` derived from teh ```Throwable``` class.

Exception has two main subclass: ```IOException``` and ```RuntimeException```
There are three categories of exceptions in Java:

| Type  | About  |
|---|---|
|  Checked Exceptions  | A checked exception is an exception that occurs at the compile time, these are also called as compile time exceptions. These exceptions cannot simply be ignored at the time of compilation, the programmer should take care of (handle) these exceptions. |
|  Unchecked Exceptions |  An unchecked exception is an exception that occurs at the time of execution. These are also called as Runtime  |
| Exceptions | These include programming bugs, such as logic errors or improper use of an API. Runtime exceptions are ignored at the time of compilation.  |

Exceptions are handled with the ```true```, ```catch```, ```throw```, and ```finally``` keywords.

```java
try {
   // Protected code
} catch (ExceptionType1 e1) {
   // Catch block
} catch (ExceptionType2 e2) {
   // Catch block
} catch (ExceptionType3 e3) {
   // Catch block
}finally {
   // The finally block always executes.
}
```

## Lambda expressions, closures, or functions as types

Java implements closures, but it is limited compared to other languages. Java uses lambda expressions and anonymous classes. These can only access the final variables of the enclosing scope. Java only saves the value of free variables to let them be used inside lambda expressions. The compiler limits the type of variable that can be used inside lambda expressions to only final and effectively final ones.

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

## Singleton

#### How is a singleton implemented?

A singleton class has:

| Type  | About  |
|---|---|
|  Static member | This contains the instance of the singleton class. |
|  Private constructor |  This will prevent anybody else to instantiate the Singleton class. |
| Static public method | This provides the global point of access to the Singleton object and returns the instance to the client calling class. |

#### Can it be made thread-safe?

Yes, by using a synchronized keyword to prevent multiple threads from accessing the singleton instance while a thread is inside the method to get the singleton instance:

```java
public static volatile SingletonExample getSingletonInstance() {
        if (null == singletonInstance) {
            synchronized (SingletonExample.class){
                    if (null == singletonInstance) {
            singletonInstance = new SingletonExample();
            }
        }
        }
        return singletonInstance;
    }
```

#### Can the singleton instance be lazily instantiated?

Yes:

```java

public class SingletonExample {
    // Static member holds only one instance of the
    // SingletonExample class
    private static SingletonExample singletonInstance;
    // SingletonExample prevents any other class from instantiating
    private SingletonExample() {
    }
    // Providing Global point of access
    public static SingletonExample getSingletonInstance() {
        if (null == singletonInstance) {
            singletonInstance = new SingletonExample();
        }
        return singletonInstance;
    }
    public void printSingleton(){
        System.out.println("Inside print Singleton");
    }
}
```

## Procedural programming

#### Does the language support procedural programming?

Yes, Java is a procedural programming language.

## Functional programming

#### Does the language support functional programming?

Java is not a functional programming language, but has support for functional programming. Lambdas were the 'solution' to allow functional programming in Java. They provide the ability to create functions at runtime which can then be passed/manipulated by other code.

## Multithreading

#### Threads or thread-like abilities

Multithreading is supported in Java. Threads are created by extending the ```Thread``` class and implementing the   ```Runnable``` interface.
When creating a class that extends ```java.lang.Thread``` we can override the ```run()``` method in the class to start the life of a thread. An object of our class is created and the ```start()``` method is called.

```java
// Java code for thread creation by extending
// the Thread class
class MultithreadingDemo extends Thread
{
    public void run()
    {
        try
        {
            // Displaying the thread that is running
            System.out.println ("Thread " +
                  Thread.currentThread().getId() +
                  " is running");

        }
        catch (Exception e)
        {
            // Throwing an exception
            System.out.println ("Exception is caught");
        }
    }
}

// Main Class
public class Multithread
{
    public static void main(String[] args)
    {
        int n = 8; // Number of threads
        for (int i=0; i<8; i++)
        {
            MultithreadingDemo object = new MultithreadingDemo();
            object.start();
        }
    }
}

```

If we create a class that implements ```java.lang.Runnable``` interface, we need to override the ```run()``` method. Then a ```Thread``` object is instantiated and the ```start()``` method is called.

```java
// Java code for thread creation by implementing
// the Runnable Interface
class MultithreadingDemo implements Runnable
{
    public void run()
    {
        try
        {
            // Displaying the thread that is running
            System.out.println ("Thread " +
                                Thread.currentThread().getId() +
                                " is running");

        }
        catch (Exception e)
        {
            // Throwing an exception
            System.out.println ("Exception is caught");
        }
    }
}

// Main Class
class Multithread
{
    public static void main(String[] args)
    {
        int n = 8; // Number of threads
        for (int i=0; i<8; i++)
        {
            Thread object = new Thread(new MultithreadingDemo());
            object.start();
        }
    }
}
```

#### How is multitasking accomplished?

To accomplish multiple tasks by multiple threads you have multiple ```run()``` methods.

```java
class Simple1 extends Thread{  
 public void run(){  
   System.out.println("task one");  
 }  
}  

class Simple2 extends Thread{  
 public void run(){  
   System.out.println("task two");  
 }  
}  

 class TestMultitasking3{  
 public static void main(String args[]){  
  Simple1 t1=new Simple1();  
  Simple2 t2=new Simple2();  

  t1.start();  
  t2.start();  
 }  
}  
```

# C# Language

## Language purpose/genesis

#### Why was the language created?
C# was created with the purpose of being a better alternative to Java.
Microsoft wanted to gain the edge in having an Object Oriented, Simple, and Modern language.

#### What problems was the language trying to address?
Similar to Java, C# was essentially addressing problems regarding low level programming
such as pointers and memory management. However, it also focused on being a better
version of Java. C# was essentially Microsoft's attempt to make an Object Oriented
language that was simple and modern. It also addressed problems such as portability and
internalization.  

#### Is the language a reaction to a previous language or a replacement for another language?
C# was Microsoft's reaction to Java. It was very similar at first, but has branched
off fairly significantly since version 2.  

## Unique features of the language
#### Does the language have any particularly unique features?
It has several rather unusual feature for a strongly typed language. Some particularly
relevant features are LINQ (Language-Integrated Query), delegation, extension
methods, properties, and the *var* keyword.  

## Name spaces
#### How are name spaces implemented?

```csharp
namespace MyApplication
{
  // The content to reside in the MyApplication namespace is placed here.
}
```

#### How are name spaces used?
They are used for file organization and to allow for classes to have the
same name. It also gives the C# compiler context for which class it is
supposed to be using. The *using* keyword can be used to tell the compiler
explicitly what namespaces you will be using in your program so that you
don't have to type out the names.
For example:

```csharp
System.Console.WriteLine();
```
vs

```csharp
using System;
// other code here
Console.WriteLine();
```

## Types
#### What types does the language support?
Value Types
* Signed integral: sbyte, short, int, long
* Unsigned integral: byte, ushort, uint, ulong
* Unicode characters: char
* IEEE floating point: float, double
* High-precision decimal: decimal
* Boolean: bool
* User-defined types of the form enum E {...}
* User-defined types of the form struct S {...}
* Extensions of all other value types with a null value

Reference Types
* Ultimate base class of all other types: object
* Unicode strings: string
* User-defined types of the form class C {...}
* User-defined types of the form interface I {...}
* Single- and multi-dimensional arrays, for example, int[] and int[,]
* User-defined types of the form delegate int D(...)

#### Are both reference and value types supported?
Yes.

#### Can new value types be created?
Yes, in the form of structs. Below is an example
```csharp
public struct CoOrds
{
    public int x, y;

    public CoOrds(int p1, int p2)
    {
        x = p1;
        y = p2;
    }
}
```

## Classes

#### Defining
```csharp
public class MyClass
{
    //Code in class such as methods, fields, etc.
}
```

#### Creating new instances
An instance of a class is created as follows:
```csharp
//Instantiation of class named NewClass with default constructor
MyClass class = new MyClass();
```
#### Constructing/initializing
```csharp
public class Point
{
    public int x, y;

    public Point() {
      //constructor with no parameters
    }
    //constructor with parameters
    public Point(int x, int y)
    {
        this.x = x;
        this.y = y;
    }
}
```

#### Destructing/de-initializing
Similar to Java there is no official destructor method. Instead you
use a Finalizer method. For example, the following is a declaration of
a finalizer for the Car class.
```csharp
class Car
{
    ~Car()  // destructor
    {
        // cleanup statements...
    }
}
```

## Instance reference name in data type (class)
#### this? self?
C# uses this to refer to a class data type as follows:
```csharp
public Employee(string name, string alias)
{
    // Use this to qualify the fields, name and alias:
    this.name = name;
    this.alias = alias;
}
```

## Properties
#### Getters and setters…write your own or built in?


#### Backing variables?
Can be explicitly declared or left to be done by the compiler. If you need
more complex logic the first example is how you should implement it.   

```csharp
public class Date
{
    private int month = 7;  // Backing store

    public int Month {
        get {
            return month;
        }
        set {
            if ((value > 0) && (value < 13)) {
                month = value;
            }
        }
    }
}
```

vs

```csharp
//backing variable is made by the compiler
public int Month { get; set; }
```

#### Computed properties?
Yes, see an example below.
```csharp
public class Person
{
    private int age;
    private int yearOfBirth;

    public int Age {
        get {
            return 2018 - yearOfBirth;
        }
        set {
            age = value;
        }
    }
}
```

## Interfaces / protocols

#### What does the language support?
Interfaces
#### What abilities does it have?
It contains only the signatures of methods, properties, events or indexers. These have to be implemented later by a struct or class.
#### How is it used?
```csharp
interface ISampleInterface
{
    void SampleMethod();
}

class ImplementationClass : ISampleInterface
{
    // Explicit interface member implementation:
    void ISampleInterface.SampleMethod()
    {
        // Method implementation.
    }

    static void Main()
    {
        // Declare an interface instance.
        ISampleInterface obj = new ImplementationClass();

        // Call the member.
        obj.SampleMethod();
    }
}
```

## Inheritance / extension

All classes derive from System.Object and inherit its methods.
```csharp
public class WorkItem
{
//some code about WorkItem. WorkItem inherits methods from Object.
}

public class ChangeRequest : WorkItem
{
// ChangeRequest extends WorkItem
}
```

Extension methods are used to let you 'add' methods to existing types when you don't control the type being extended and you don't want to force whoever is implementing it to provide code that can be done using the existing methods.

```csharp
class ExtensionMethods2    
{

    static void Main()
    {            
        int[] ints = { 10, 45, 15, 39, 21, 26 };
        var result = ints.OrderBy(g => g);
        foreach (var i in result)
        {
            System.Console.Write(i + " ");
        }           
    }        
}
//Output: 10 15 21 26 39 45

```

Reflection

* What reflection abilities are supported?

 Reflection is used to discover information about a  program entity at run time and to create instance of a type at runtime.
 Most of the classes and interfaces needed for reflection are found in the System.Reflection namespace.

 In the System.Reflection namespace, these are the main classes defined:

|  Assembly       | Represents an assembly|
| EventInfo       |This class holds information for a given event.|
| FieldInfo       |This class holds information for a given field.|
| MemberInfo      |Class is the abstract base class for classes used to obtain information about all members of a class. |
| MethodInfo      |This class contains information for a given method.|
| ConstructorInfo |This class contains information for a given constructor.|

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

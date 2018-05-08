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
methods, properties, and the ```var``` keyword.  

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
supposed to be using. The ```using``` keyword can be used to tell the compiler
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
C# uses ```this``` to refer to a class data type as follows:
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
Can be written yourself or left to be done by the compiler. (See below examples)

#### Backing variables?
Can be explicitly declared or left to be done by the compiler. If you need
more complex logic, the first example is how you should implement it.   

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

## Reflection

#### What reflection abilities are supported?

 Reflection is used to discover information about a  program entity at run time and to create instance of a type at runtime.
 Most of the classes and interfaces needed for reflection are found in the System.Reflection namespace.

 In the System.Reflection namespace, these are the main classes defined:

| Classes   | About  |
|---|---|
|  Assembly   | Represents an assembly  |
|  EventInfo |  This class holds information for a given event. |
| FieldInfo  | This class holds information for a given field.  |
|  MemberInfo  | Class is the abstract base class for classes used to obtain information about all members of a class. |
| MethodInfo  | This class contains information for a given method. |
| ConstructorInfo  | This class contains information for a given constructor. |

#### How is reflection used?

Reflection is used in C# to retrieve metadata on types at runtime. Reflection is used to inspect metadata of the types in your program at runtime, so you can retrieve information on the loaded assemblies and the types defined in them.

## Memory management

#### How is it handled?

Memory allocated on the heap is managed automatically. It is required that all resources be allocated from the managed heap. Objects are automatically freed when they are no longer needed by the application.

#### How does it work?

When a process is initialized, the runtime reserves a contiguous region of address space (the managed heap) with no storage allocated for it. This heap also maintains a pointer which indicates where the next object will be allocated within the heap. The pointer is initially set to the base address of the reserved address space region. When the 'new' operator is used to create an object, it is first checked that there are enough bytes. If there are not enough bytes, then a collection of unused memory is performed.

#### Garbage collection?

The garbage collector checks if there are any objects in the heap no longer being used. The memory of these objects is reclaimed when they are not used. If there is no more memory available then an OutOfMemoryException is thrown. The garbage collector checks all of the roots and creates a graph that contains the set of all objects somehow reachable by the application's roots. If an object is not in the graph, it isn't accessible and considered garbage.

#### Automatic reference counting?

Automatic reference counting manages object life cycles by keeping track of all valid references to an object with an internal retain count. There is no reference-counted objects to be used explicitly in C# because garbage collection is used.

## Comparisons of references and values

#### How are values compared? (i.e. comparing two strings)

== can be used to compare null values

```csharp
string x = null;
string y = null;

if (x.Equals(y)) // Messes up

if (x == y) // Yes
```
You can use ```object.Equals``` to avoid the problem with null comparisons

```csharp
if (object.Equals(x, y)) // Fine even if x or y is null
```

For Case Sensitive Comparison

```csharp
string string1 = "Something";
string string2 = "Something";

if (string1.Equals(string2,StringComparison.Ordinal))
{
 //Strings are Equal
}
else
{
 //Strings are not Equal
}
```

For Case Insensitive Comparison

```csharp
string string1 = "Something";
string string2 = "Something";

if (string1.Equals(string2,StringComparison.OrdinalIgnoreCase))
{
 //Strings are Equal
}
else
{
 //Strings are not Equal
}
```


#### Which does the language use? (null/nil/etc)

C# uses the ```null ``` keyword as a literal that represents a null reference.

#### Does the language have features for handling null/nil references?

C# has NullReferenceExceptions that occur when you try to use a method with the value of null.

## Errors and exception handling

Exceptions handling is built upon 'try', 'catch', 'finally', and 'throw'.

| Name   | About  |
|---|---|
|  try   | A try block identifies a block of code for which particular exceptions is activated. It is followed by one or more catch blocks. |
|  catch |  A program catches an exception with an exception handler at the place in a program where you want to handle the problem. The catch keyword indicates the catching of an exception. |
| finally | The finally block is used to execute a given set of statements, whether an exception is thrown or not thrown. For example, if you open a file, it must be closed whether an exception is raised or not. |
|  throw  | A program throws an exception when a problem shows up. This is done using a throw keyword. |

```csharp
try {
   // statements causing exception
} catch( ExceptionName e1 ) {
   // error handling code
} catch( ExceptionName e2 ) {
   // error handling code
} catch( ExceptionName eN ) {
   // error handling code
} finally {
   // statements to be executed
}
```

Exceptions are handled by classes. These classes are derived from the System.Exception class. Other classes derived from this are System.ApplicationException and System.SystemException.

System.ApplicationException supports exceptions generated by applications programs. The exceptions are defined by the programmers.

System.SystemException is the base class for all predefined system exceptions.

An example of throwing an exception when dividing by zero:

```csharp
using System;

namespace ErrorHandlingApplication {
   class DivNumbers {
      int result;

      DivNumbers() {
         result = 0;
      }
      public void division(int num1, int num2) {
         try {
            result = num1 / num2;
         } catch (DivideByZeroException e) {
            Console.WriteLine("Exception caught: {0}", e);
         } finally {
            Console.WriteLine("Result: {0}", result);
         }
      }
      static void Main(string[] args) {
         DivNumbers d = new DivNumbers();
         d.division(25, 0);
         Console.ReadKey();
      }
   }
}
```

```csharp
Exception caught: System.DivideByZeroException: Attempted to divide by zero.
at ...
Result: 0
```
## Lambda expressions, closures, or functions as types

C# supports first class functions or functions as types.

Using anonymous methods:
```csharp
Func<string,string> myFunc = delegate(string var1)
                                {
                                    return "some value";   
                                };
```

Using lambdas:
```csharp
Func<string,string> myFunc = var1 => "some value";
```
The C# compiler detects when a delegate forms a closure which is passed out of the current scope and it promotes the delegate, and the associated local variables into a compiler generated class. You can use closures like this:

```csharp
static void Main(string[] args)
{
    var inc = GetAFunc();
    Console.WriteLine(inc(5));
    Console.WriteLine(inc(6));
}

public static Func<int,int> GetAFunc()
{
    var myVar = 1;
    Func<int, int> inc = delegate(int var1)
                            {
                                myVar = myVar + 1;
                                return var1 + myVar;
                            };
    return inc;
}
```
## Implementation of listeners and event handlers

C# has an ``` EventHandler ```. C#'s EventHandler is a delegate or strongly typed pointer to method that handles an event.

```csharp
Button.Click += new EventHandler(MyButton_Click);

private void MyButton_Click(object sender, EventArgs e)
{
    doSomething();
}
```

## Singleton

#### How is a singleton implemented?
A singleton is implemented by a single constructor which is private and parameterless. It has a static variable that holds a reference to the single created instance, if any. It is also necessary to have a public static means of getting the reference to the single created instance.

#### Can it be made thread-safe?

Yes

```csharp
public sealed class Singleton
{
    private static readonly Singleton instance = new Singleton();

    // Explicit static constructor to tell C# compiler
    // not to mark type as beforefieldinit
    static Singleton()
    {
    }

    private Singleton()
    {
    }

    public static Singleton Instance
    {
        get
        {
            return instance;
        }
    }
}
```

#### Can the singleton instance be lazily instantiated?

Yes

```csharp
public sealed class Singleton
{
    private Singleton()
    {
    }

    public static Singleton Instance { get { return Nested.instance; } }

    private class Nested
    {
        // Explicit static constructor to tell C# compiler
        // not to mark type as beforefieldinit
        static Nested()
        {
        }

        internal static readonly Singleton instance = new Singleton();
    }
}
```

## Procedural programming

#### Does the language support procedural programming?

Yes. C# was designed to primarily support imperative (procedural) programming. This is where a developer writes codes that describes in detail the steps that the computer must take to accomplish the goal.

## Functional programming

#### Does the language support functional programming?

Functional programming involves composing the problem as a set of functions to be executed. The input and return type of each function is carefully defined. C# is used for procedural programming but has explicit language extensions that support functional programming. These are lambda expressions and type interface. LINQ technology is a form of declarative functional programming.

## Multithreading

#### Threads or thread-like abilities

C# uses the System.Threading.Thread class to work with threads. It allows creating and accessing individual threads in a multithreaded application. A thread ends with the delegate passed to the Thread's constructor finishes executing. Once it ends, a thread cannot restart.

#### How is multitasking accomplished?

C# supports parallel execution of code through multithreading. A single thread is created automatically by the CLR and OS. this is made multithreaded by adding additional threads.

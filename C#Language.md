# C# Language

Language purpose/genesis

* Why was the language created?
* What problems was the language trying to address?
* Is the language a reaction to a previous language or a replacement for another language?

Unique features of the language

* Does the language have any particularly unique features?
Name spaces

* How are name spaces implemented?
* How are name spaces used?

Types

* What types does the language support?
* Are both reference and value types supported?
* Can new value types be created?

Classes

* Defining
* Creating new instances
* Constructing/initializing
* Destructing/de-initializing

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

- All classes derive from System.Object and inherit its methods.
```C#
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

```C#
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

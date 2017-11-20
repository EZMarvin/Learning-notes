# C SHARP #

 COM(Component Object Model) => for desktop application

    OOP Language program => compile
    Assembly - CIL Code
    CLR - machine code

    CSC filename / ildasm (反编译) show CIL code
    GAC ????

## CLR ##

compile CIL into native code

* memeory management
* application hosting
* coordinating thread
* performing
* security checks

manage code - under CLR control (have memeory management)

unmanage code - not under CLR control (no memory management) (**Idisposable**)

## CTS CLS BCL ##

CTS(common type system) - describe all data types and programming constructs supported by the run time, how they represented in the .NET format

CLS(common language specification) - defines a subset of common types and programming constructs that .NET programming language can agree on (basic library)

BCL - provide a base class library that is available to all .NET programming language.

## Dot Net Framework ##

os - manage resource, process
CLR - manage execution of NET code, memeory, concurrency, security
BCL - library with fundamental class
Data Tier - database access, XML support
WCF - windows communication foundation windows wordflow foundation WWF
Interface tech - web based and windows GUI

## process thread ##

## GAC ##

Global Assembly Cache :-- Assemblies can be shared among multiple applications on the machine by registering them in global Assembly cache(GAC).

Each computer where the common language runtime is installed has a machine-wide code cache called the global assembly cache. The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.

GAC is a machine wide a local cache of assemblies maintained by the .NET Framework. We can register the assembly to global assembly cache by using gacutil command. 

We can Navigate to the GAC directory, C:\winnt\Assembly in explore. In the tools menu select the cache properties; in the windows displayed you can set the memory limit in MB used by the GAC

## layer and tier ##

Layer is logical - Logical layers are merely a way of organizing your code. Typical layers include Presentation, Business and Data – the same as the traditional 3-tier model.

Tier is physical - tiers are places where layers are deployed and where layers run. In other words, tiers are the physical deployment of layers.

## variable scope ##

member/Field var
Local var
Local var inside statement

## Datatype ##

by default all number with decimal point is **double**
if use float use **5.2f**

## Function ##

### variable used in function ###

* passing by reference - change of formal parameter will be reflect in actual parameter (ref int a, ref int b)

* passing by value - a new copy gets passed to method. so the change will not reflect to actual par (int a, int b) (formal parameter)

* out parameter - (out string msg)

* assign value to par - (optional parameter) (int a = 3) 这个值可以不提供 optional parameter must after the required parameters 在正常的变量之后

* (params int[] arg) - group of parameters

* assign without obey of order fucntion(a: 10, b: 10, c: 20)

### value and ref ###

gc work with reference
value in stack
reference in heap

## constructor ##

1. special member function which share the name of the class
1. never return any vlaue
1. Constructor can take parameters so it can be overloaded
1. used to initialize the class member
1. consturctor is used to create an new object of class
1. if no constructor then .net will create default constructor
1. if you create your custom constructor then the default will be replace
1. can be inherited so it can not be override

### static constructor ###

1. class can have both static and non static constructor
1. static constructor can not have access modifier
1. you can not call static constructor explicitly. Static constructor executes automatically before any non static constructor of that class
1. static constructor can not accept parameter

static class and seal class can not be inherit

## method hidding and method override ##

public new void printCustomer(){}

A a = new B(); call base class method **virtual method also work**

public override printCustomer(){} **require virtual method**

A a = new B(); call derived/subclass class method

## Abstract Class Method ##

1. Abstract class is a class that will always serve as base class and it can not be instantiated
1. Abstract class must use abstract keyword
1. it should have at least one abstract method
1. can have both abstract and non-abstract method
1. can have constructor
1. abstract method is just declared in the abstract class and implemented in derived class
1. abstract method is by default virtual so can not add virtual keyword

## Interface ##

1. by default all method in interface are abstract
1. by default public can not change their access modifier
1. supports multiple inheritance
1. interface can not have constructor
1. can not create object of an interface
1. interface help loose couple code

## Collection ##

generic <> and non-generic (any type)

value -> ref boxing || ref -> value unboxing

method<T>(T a, T b) - type safe use **a.Equals(b)**

class() where T: class/Struct/interface/new object

    Non-generic         |       Generic
    IEnumerator         |       IEnumerator<T>
    IEnumerable         |       IEnumerable<T>
    ICollection         |       ICollection<T>
        /      \        |           /     \
    IDictionary IList   |   IDictionary<> IList<>

Relaional??

* Dictionary<Tkey, Tvalue>
* SortedDictionary<Tkey, Tvalue> binary tree
* SortedList<Tkey, Tvalue> in Array

NonRelational

* List<> primary Length 4
* LinkedList<> 
* HashSet<>
* SortedSet<>
* Stack<>
* Queue<>

ArrayList -> List<>
HashTable -> Dictionary<>
Queue -> Queue<>
Stack -> Stack<>
SortedList -> SortedList<>

## Exception Handle ##

exception runtime error - logical mistake

```C#
try {

}
catch(OverFlowException oe){

}
catch(Exception ex){

}
finally{

}
```

catch order from specific to general

    Object
      |
    Exception
        |                   \
        SystemException     ApplicationException
        |                       |
        Build in exception      Custom Exception
        throw new Exception

Check input is Number or not **int.TryParse(input, out x)** return true if success

## Attribute ##

```C#
[obsolute("use addnumber function")]
function () // when use will get notification

[obsolute("", true)]
function () // will get error
```

## Extension Method ##

1. extension method must be static
1. class contain extension method must be static
1. first para must of the type which you want to extend and written after this key word

```C#
public static bool isprime (this int x){

}
```

## static method - shared method ##

Compile time and shared memory

## partial classes ##

partial class can use same name in namespace 一个class分成好几个部分编写

## Constant Readonly ##

1. value of con can not change through program, readonly can change in constructor
1. con must be initialized when declared, readonly is not must can declared later in constructor
1. const can not be static, can not add static keyword with con. readonly can add static

## Var || dynamic type ##

compile time || runtime

var must assign value || dynamic don't need

var in program can not change || dynamic can change value type

## Delegate ##

type safe function pointer

    Predefine delegate - generic
    Action - any type input no output
    Func - any input any output
    Predicate - any type input ouput pool

## Event ##

A mechanism for communication between two object

Lose Coupling

Help extend application
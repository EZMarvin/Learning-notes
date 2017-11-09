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

You should share assemblies by installing them into the global assembly cache only when you need to. As a general guideline, keep assembly dependencies private, and locate assemblies in the application directory unless sharing an assembly is explicitly required. In addition, it is not necessary to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.

GAC is a machine wide a local cache of assemblies maintained by the .NET Framework. We can register the assembly to global assembly cache by using gacutil command. 

We can Navigate to the GAC directory, C:\winnt\Assembly in explore. In the tools menu select the cache properties; in the windows displayed you can set the memory limit in MB used by the GAC

## Namespace ##

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
1. class can have both static and non static constructor
1. static con can not have access modifier
1. 

static class and seal class can not be inherit

## method hidding and method override ##

public new void printCustomer(){}

A a = new B(); call base class method

public override printCustomer(){}

A a = new B(); call derived/subclass class method

## Collection ##

generic and non-generic



## Attribute ##

```C#
[obsolute("use addnumber function")]
function () // when use will get notification

[obsolute("", true)]
function () // will get error
```

## Array ##

Array.Sort();
Array.Reverse();

## layer and tier ##

Layer is logical - Logical layers are merely a way of organizing your code. Typical layers include Presentation, Business and Data – the same as the traditional 3-tier model.

Tier is physical - tiers are places where layers are deployed and where layers run. In other words, tiers are the physical deployment of layers.
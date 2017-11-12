# JAVA #

总结

## Syntax ##

* Object is a runtime entity and it's state is stored in field and behaviour
* Class is blue print to create object, describe status and behaviour
* Methods is behaviour (write logic, mantipulate data, and execute action)
* Constructor is invoked when new object is created
* Creating object - declared, instantiated, initialized

## Modifiers ##

* Access Modifiers - default, public(visable to world), protected(visable to package and subclass), private(to class only)
* Non-access Modifiers - static, final(finalize the implementation of class, method, and variable), abstract(abstract class), synchronized volatile (thread)

## Variables ##

* Local Variables - inside the method, constructors, or blocks, destory when method complete **No access modifiers/ No default value**
* Class variables (Static) - declare within a class, outside method. **with static keyword**
* Instance Variables (Non-static) - variables within a class but outside any method, initialized when class is instantiated

## Boxing and Unboxing ##

* converting primitive data type into object is boxing
* converting back is unboxing 

## Constructor ##

* can't be final, abstract, static (没有意义，本身已经包含这些定义)
* can be private (可以，singleton)

## finalize() method ##

* called before an object's final destruction - used to make sure object terminates cleanly

## OOP ##

* Inheritance (extends)
  * can be defined as the process where one class need properties of another
  * reuse the field and method of the existing class
* Polymorphism (when a parent class reference is used to refer to child class object)
    * ability of an object to take on many forms
* Abstraction (abstract class and interface)
    * a process of hiding the implementation details from user, only functionality will be provided to the user
* Encapsulation
    * a mechanism of wrapping the data and code acting on data together as a single unit
    * data will be hiding from other class - data hidning 
    * private class variable and provide setter and getter methods

## Exception ##

* checked exceptions - exception that occurs at compile time
* unchecked exception - runtime exception
* Throws- method does not handle a checked exception, method must declare it using throws
  * use to postpone the handling of checked exception
  * followed by exception class names
  * can throw multiple exception 

```java

void sample() throws ExceptionClass, NullPointerException {

}
```

* Throw - throw an exception 
    - invoke an exception explicitly
    - followed by an instance of exception
    - throw one at a time

``` java

try {
    throw new ErrorClass();
} 
catch (Exception e) {
    System.out.println(e);
}
```

* Finally block
  * follows a try block or catch block
  * block of code will always executes (不管是否有exception)

## Inner Class (Nested) ##

* Inner Class - security mechanism/ can use private/ can use access private member

```java

class Outer_Demo {
   int num;
   // inner class
   private class Inner_Demo {
      public void print() {
         System.out.println("This is an inner class");
      }
   }
   // Accessing he inner class from the method within
   void display_Inner() {
      Inner_Demo inner = new Inner_Demo();
      inner.print();
   }
}
public class My_class {

   public static void main(String args[]) {
      // Instantiating the outer class 
      Outer_Demo outer = new Outer_Demo(); 
      // Accessing the display_Inner() method.
      outer.display_Inner();
   }
}
```

* Method-local inner class - write a class within a method and this will be a local type/ can only be used within the method

```java
public class Outerclass {
   // instance method of the outer class 
   void my_Method() {
      int num = 23;

      // method-local inner class
      class MethodInner_Demo {
         public void print() {
            System.out.println("This is method inner class "+num);	   
         }   
      } // end of inner class

      // Accessing the inner class
      MethodInner_Demo inner = new MethodInner_Demo();
      inner.print();
   }

   public static void main(String args[]) {
      Outerclass outer = new Outerclass();
      outer.my_Method();
   }
}
```

* Anonymous Inner Class - inner class declare without a class name/ declare and instantiate at the same time/ used when need override the method of a class or interface 

```java
abstract class AnonymousInner {
   public abstract void mymethod();
}

public class Outer_class {

   public static void main(String args[]) {
      AnonymousInner inner = new AnonymousInner() {
         public void mymethod() {
            System.out.println("This is an example of anonymous inner class");
         }
      };
      inner.mymethod();	
   }
}
```

* Static Nested Class - inner class which is a static member of outer class/ can be accessed without instantiating the outer class

```java
public class Outer {
   static class Nested_Demo {
      public void my_method() {
         System.out.println("This is my nested class");
      }
   }

   public static void main(String args[]) {
      Outer.Nested_Demo nested = new Outer.Nested_Demo();	 
      nested.my_method();
   }
}
```

## OverLoading VS Overriding ##

* Rules for Overriding
  * argument list should be exactly the same as the overriden method
  * return type should be the same or a subtype of the return type
  * access level can not be more restrictive than the overriden method 重写后访问条件更加宽松
  * final method can not override
  * overriding method can throw narrower or fewer exceptions than overridden method 

| Overloading    | Overriding   |
| -------- | -----  |
| compile-time - call to its definition | runtime - call to its definition   |
| Static method can be overloaded (class can have multiple static method with same name) | Static method can not be override |
| Static binding | dynamtic binding |
| private and final method can overload | no override |
| return type does not matter | must be same or more specified (subtype) |
| Argument should be different | Argument should be same |

## Interfaces & abstract class ##

* Interfaces
    * can be defined as a contract between objects on how to communicate with each other, describe the behaviour
    * a reference type in java, a collection of abstract methods
    * may contain constants, default method, static method
    * all method need to be defined in class unless it was implemented by abstract class
    * no instance
    * no constructors
    * only field is static and final
    * one class can extend multiple interfaces

* Abstract Class
    * may or may not contain abstract methods
    * if have one abstract method then is have to be abstract 
    * absctract class can not be instantiated
    * use abstract class you have to inherit it and provide implementation to abstract methods
    * if you inherit abstract class, you have to provide implementations to all abstract methods in it

| Abstract Class | Interface |
| -------- | -------- |
| can have constructor | no constructor |
| can extend one class or one abstract class | can extend any number of interfaces at a time |
| can extend concrete class | only extend interface |
| can have abstract and concrete methods | only abstract method |
| can have protect and public abstract nethods | only public methods |
| can have static and final or static final variable with access profiler | only public static final variable |

## Thread ##

* Create thread by implementing a Runable Interface

```java
class RunnableDemo implements Runnable {
   private Thread t;
   private String threadName;

   RunnableDemo( String name) {
      threadName = name;
      System.out.println("Creating " +  threadName );
   }

   public void run() {
      System.out.println("Running " +  threadName );
      try {
         for(int i = 4; i > 0; i--) {
            System.out.println("Thread: " + threadName + ", " + i);
            // Let the thread sleep for a while.
            Thread.sleep(50);
         }
      }catch (InterruptedException e) {
         System.out.println("Thread " +  threadName + " interrupted.");
      }
      System.out.println("Thread " +  threadName + " exiting.");
   }

   public void start () {
      System.out.println("Starting " +  threadName );
      if (t == null) {
         t = new Thread (this, threadName);
         t.start ();
      }
   }
}

public class TestThread {

   public static void main(String args[]) {
      RunnableDemo R1 = new RunnableDemo( "Thread-1");
      R1.start();

      RunnableDemo R2 = new RunnableDemo( "Thread-2");
      R2.start();
   }
}
```

* Create thread by extending a thread class

```java
class ThreadDemo extends Thread {
   private Thread t;
   private String threadName;

   ThreadDemo( String name) {
      threadName = name;
      System.out.println("Creating " +  threadName );
   }

   public void run() {
      System.out.println("Running " +  threadName );
      try {
         for(int i = 4; i > 0; i--) {
            System.out.println("Thread: " + threadName + ", " + i);
            // Let the thread sleep for a while.
            Thread.sleep(50);
         }
      }catch (InterruptedException e) {
         System.out.println("Thread " +  threadName + " interrupted.");
      }
      System.out.println("Thread " +  threadName + " exiting.");
   }

   public void start () {
      System.out.println("Starting " +  threadName );
      if (t == null) {
         t = new Thread (this, threadName);
         t.start ();
      }
   }
}

public class TestThread {

   public static void main(String args[]) {
      ThreadDemo T1 = new ThreadDemo( "Thread-1");
      T1.start();

      ThreadDemo T2 = new ThreadDemo( "Thread-2");
      T2.start();
   }
}
```

## Java Collection & Map ##

      Collection                Map
       / /  \      \             |
    Set List Queue <- Dequeue  SortedMap
    |
    SortedSet

List: ArrayList / LinkedList / Stack / Vector
Set: HashSet / LinkedHashSet / TreeSet
Queue: PriorityQueue / ArrayDeque(Deque) = new LinkedList() / LinkedList(Deque)
Map: HashMap / HashLinkedMap / HashTable / TreeMap
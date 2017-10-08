## JAVA
### OverLoading VS Overriding
* Rules for Overriding
    * argument list should be exactly the same as the overriden method
    * return type should be the same or a subtype of the return type
    * access level can not be more restrictive than the overriden method
    * final method can not override
    * overriding method can throw narrower or fewer exceptions than overridden method 

| Overloading    | Overriding   |
| -------- | -----  |
| compile-time - call to its definition | runtime - call to its definition   |
| Static method can be overloaded (class can have multiple static method with same name) | Static method can not be override |
| Static binding | dynamtic binding |
| Performance better done at runtime |  |
| private and final method can overload | no override |
| return type does not matter | must be same or more specified (subtype) |
| Argument should be different | Argument should be same |

### Syntax
* Object have states and behaviour
* Class define a tempalte that describe status and behaviour
* Methods is behaviour (write logic, mantipulate data, and execute action)
* Instance Variables - object's state is create by the value assigned to these variables

### Modifiers
* Access Modifiers - default, public(visable to world), protected(visable to package and subclass), private(to class only)
* Non-access Modifiers - static, final(finalize the implementation of class, method, and variable), abstract(abstract class), synchronized volatile (thread)

### Variables 
* Local Variables - inside the method, constructors, or blocks, destory when method complete **No access modifiers/ No default value**
* Class variables (Static) - declare within a class, outside method. **with static keyword**
* Instance Variables (Non-static) - variables within a class but outside any method, initialized when class is instantiated

### Boxing and Unboxing
* converting primitive data type into object is boxing
* converting back is unboxing 

### finalize() method 
* called before an object's final destruction - used to make sure object terminates cleanly

### OOP
* Inheritance (extends)
    * can be defined as the process where one class need properties of another
    * reuse the field and method of the existing class
* Polymorphism (when a parent class reference is used to refer to child class object)
    * ability of an object to take on many forms
* Abstraction
    * a process of hiding the implementation details from user, only functionality will be provided to the user
* Encapsulation
    * a mechanism of wrapping the data and code acting on data together as a single unit
    * data will be hiding from other class - data hidning 
    * private class variable and provide setter and getter methods

### Exception
* checked exceptions - exception that occurs at compile time
* unchecked exception - runtime exception
* Throws- method does not handle a checked exception, method must declare it using throws 
    - use to postpone the handling of checked exception
    - followed by exception class names
    - can throw multiple exception 
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
    - follows a try block or catch block
    - block of code will always executes (不管是否有exception)

### Inner Class
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
### Interfaces & abstract class

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


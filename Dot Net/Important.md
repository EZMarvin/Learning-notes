# IMPORTANT #

## Extension Method ##

Linq IEnumerable Where

WHY extension method

* add method on existing method
* used when you don't have access to source code (don't own the class)

HOW to implement and call extension method

1. Define a static class to contain the extension method.
1. The class must be visible to client code. For more information about accessibility rules, see Access Modifiers.
1. Implement the extension method as a static method with at least the same visibility as the containing class.
1. The first parameter of the method specifies the type that the method operates on; it must be preceded with the this modifier.
1. In the calling code, add a using directive to specify the namespace that contains the extension method class.
1. Call the methods as if they were instance methods on the type.

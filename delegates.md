
Delegates
---------

A delegate declaration defines a method type: a type that can be invoked, accepting a set of values of certain types, and returning a value of a set type. In Vala, methods are not first-class objects, and as such cannot be created dynamically; however, any method can be considered to be an instance of a delegate's type, provided that the method signature matches that of the delegate.

Methods are considered to be an immutable reference type. Any method can be referred to by name as an expression returning a reference to that method - this can be assigned to a field (or variable, or parameter), or else invoked directly as a standard method invocation (see
[Expressions/Invocation expressions](invocation-expressions.md)).



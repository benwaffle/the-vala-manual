Methods
-------

A method is an executable statement block that can be identified in one or more ways (i.e. by a name, or any number of delegate instances). A method can be invoked with an optional number of parameters, and may return a value. When invoked, the method's body will be executed with the parameters set to the values given by the invoker. The body is run in sequence until the end is reached, or a return statement is encountered, resulting in a return of control (and possibly some value, in the case of a return) to the invoker.

There are various contexts that may contain method declarations (see [Namespaces](namespaces.md), 
[Classes](classes.md), [Interfaces](interfaces.md), [Structs](structs.md)). A method is always declared inside one of these other declarations, and that declaration will mark the parent scope that the method will be executed within. See [Concepts/Scope and naming](scope-and-naming.md).

The [Classes](classes.md) section of this documentation talks about both methods and abstract methods. It should be noted that the latter are not truly methods, as they cannot be invoked. Instead, they provide a mechanism for declaring how other methods should be defined. See [Classes](classes.md) for a description of abstract methods and how they are used.

The syntax for invoking a method is described on the expressions page (see [Expressions/Invocation expressions](invocation-expressions.md)).






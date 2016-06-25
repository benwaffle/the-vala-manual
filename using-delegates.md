

Using delegates
===============

A delegate declaration defines a type. Instances of this type can then be assigned to variables (or fields, or paramaters) of this type. Vala does not allow creating methods at runtime, and so the values of delegate-type instances will be references to methods known at compile time. To simplify the process, inline methods may be written (see [Methods/Lambdas](lambdas.md)).

To call the method referenced by a delegate-type instance, use the same notation as for calling a method. Instead of giving the method's name, give the identifier of the variable, as described in [Expressions/Invocation expressions](invocation-expressions.md).


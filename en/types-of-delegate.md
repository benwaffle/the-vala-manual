

Types of delegate
=================

All delegate types in Vala are defined to be either static or instance delegates. This refers to whether the methods that may be considered instances of the delegate type are instance members of classes or structs, or not.

To assign an instance of an instance delegate, you must give the method name qualified with an identifier that refers to a class or struct instance. When an instance of an instance delegate is invoked, the method will act as though the method had been invoked directly: the "this" keyword will be usuable, instance data will be accessible, etc.

Instance and static delegate instances are not interchangeable.


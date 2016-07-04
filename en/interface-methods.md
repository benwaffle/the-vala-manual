

Interface methods
=================

Interfaces can contain abstract and non abstract methods. A non-abstract class that implements the interface must provide implementations of all abstract methods in the interface. All methods defined in an interface are automatically virtual.

Vala interfaces may also define static methods. These are equivalent to static methods in classes.

-   interface-instance-method-declaration:

    -   [ class-member-visibility-modifier ] return-type method-name **(** [ params-list ] **)** method-contracts [ **throws** exception-list ] **{** statement-list **}**


-   interface-instance-abstract-method-declaration:

    -   [ class-member-visibility-modifier ] **abstract** return-type method-name **(** [ params-list ] **)** method-contracts [**throws** exception-list ] **;**


-   interface-static-method-declaration:

    -   [ class-member-visibility-modifier ] **static** return-type method-name **(** [ params-list ] **)** method-contracts [**throws** exception-list ] **{** statement-list **}**


For discussion of methods in classes, see: [Classes/Class methods](class_methods.md). For information about methods in general, see [Methods](methods.md). Of particular note is that an abstract method of an interface defines a method that can always be called in an instance of an interface, because that instance is guaranteed to be of a non-abstract class that implements the interface's abstract methods.

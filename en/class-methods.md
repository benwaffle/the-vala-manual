

Class methods
=============

Class methods are methods bound to a particularly class or class instance, i.e. they are executed within the scope of that class or class instance. They are declared the same way as other methods, but within the declaration of a class.

The same visibility modifiers can be used as for fields, although in this case they refer to what code can call the methods, rather than who can see or change values.

The `static` modifier is applicable to methods also. A static method is independent of any instance of the class. It is therefore only in the class scope, and may only access other `static` members.

-   class-instance-method-declaration:

    -   [ class-member-visibility-modifier ] [ class-method-type-modifier ] return-type method-name **(** [ params-list ] **)** method-contracts [ **throws** exception-list] **{** statement-list **}**


-   class-class-method-declaration:

    -   [ class-member-visibility-modifier ] **class** return-type method-name **(** [ params-list ] **)** method-contracts [ **throws** exception-list ] **{** statement-list **}**


-   class-static-method-declaration:

    -   [ class-member-visibility-modifier ] **static** return-type method-name **(** [ params-list ] **)** method-contracts [ **throws** exception-list ] **{** statement-list **}**


-   class-method-type-modifier:

    -   **virtual**

    -   **override**

Methods can be virtual, as described in [Concepts/Object oriented programming](object_oriented_programming.md). Methods in Vala classes are not virtual automatically, instead the "virtual" modifier must be used when it is needed. Virtual methods will only chain up if overridden using the override keyword.

Vala classes may also define abstract methods, by writing the declaration with the "abstract" modifier and replacing the method body with an empty statement ";". Abstract methods are not true methods, as they do not have an associated statement block, and so cannot be invoked. Abstract methods can only exist in abstract classes, and must be overridden in derived classes. For this reason an abstract method is always virtual.

The purpose of an abstract method is to define methods that all non-abstract subclasses of the current definition must implement, it is therefore always allowable to invoke the method on an instance of the abstract class, because it is required that that instance must in fact be of a non-abstract subclass.

-   class-instance-abstract-method-declaration:

    -   [ class-member-visibility-modifier ] **abstract** return-type method-name **(** [ params-list ] **)** method-contracts [ **throws** exception-list ] **;**

> **Note**
>
> *Virtual methods are not available to compact classes.*


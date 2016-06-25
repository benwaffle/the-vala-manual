

Class declaration
=================

-   class-declaration:

    -   [ access-modifier ] **class** qualified-class-name [
        inheritance-list ] **{** [ class-members ] **}**

-   qualified-class-name:

    -   [ qualified-namespace-name **.** ] class-name

-   class-name:

    -   identifier

-   inheritance-list:

    -   **:** superclasses-and-interfaces

-   superclasses-and-interfaces:

    -   ( qualified-class-name | qualified-interface-name ) [ **,** superclasses-and-interfaces ]

-   class-members:

    -   class-member [ class-members ]

-   class-member:

    -   class-creation-method-declaration

    -   class-constructor-declaration

    -   class-destructor-declaration

    -   class-constant-declaration

    -   class-delegate-declaration

    -   class-enum-declaration

    -   class-instance-member

    -   class-class-member

    -   class-static-member

    -   inner-class-declaration

-   class-constructor-declaration:

    -   class-instance-constructor-declaration

    -   class-class-constructor-declaration

    -   class-static-constructor-declaration

-   class-instance-member:

    -   class-instance-field-declaration

    -   class-instance-method-declaration

    -   class-instance-property-declaration

    -   class-instance-signal-declaration

-   class-class-member:

    -   class-class-field-declaration

    -   class-class-method-declaration

    -   class-class-property-declaration

-   class-static-member:

    -   class-static-field-declaration

    -   class-static-method-declaration

    -   class-static-property-declaration

-   inner-class-declaration:

    -   [ access-modifier ] **class** class-name [ inheritance-list ] **{** [ class-members ] **}**

In Vala, a class must have either one or zero superclasses, where have zero superclasses has the result described in [Classes/Types of class](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#Types_of_class) section. A class must meet all the prerequisites defined by the interfaces it wishes to implement, by implementing prerequisite interfaces or inheriting from a particular class. This latter requirement means it is potentially possible to have two interfaces that cannot be implemented by a single class.

> **Note**
>
> Interfaces are only supported for GType classes. Compact
> classes have access only to a limited form of inheritence, whereby
> they may inherit from exactly one or zero other compact classes.
>
> When declaring which class, if any, a new class subclasses, and which
> interfaces it implements, the names of those other classes or
> interfaces can be qualified relative to the class being declared. This
> means that, for example, if the class is declared as "class foo.Bar"
> (class "Bar" in namespace "foo") then it may subclass class "Base" in
> namespace "foo" simply with "class foo.Bar : Base".

If an access modifier for the class is not given, the default "public" is used.

It is possible to declare a class definition to be "abstract." An abstract class is one they may not be instantiated, instead it first be subclassed by a non-abstract ("concrete") class. An abstract class declaration may include abstract class instance members. These act as templates for methods or properties that must be implemented in all concrete subclasses of the abstract class. It is thus guaranteed that any instance of the abstract class (which must be in fact an instance of a concrete subclass) will have a method or property as described in the abstract class definition.

-   abstract-class-declaration:

    -   [ access-modifier ] **abstract** **class** qualified-class-name [ inheritance-list ] **{** [ abstract-class-members ] **}**

-   abstract-class-members:

    -   class-members

    -   class-instance-abstract-method-declaration

    -   class-instance-abstract-property-declaration

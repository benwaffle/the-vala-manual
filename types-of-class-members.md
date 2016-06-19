

Types of class members
======================

There are three fundamentally different types of class members,
instance, class and static.

-   Instance members are held per instance of the class. That is, each
    instance has its own copies of the members in its own instance
    scope. Changes to instance fields will only apply to that instance,
    calling instance methods will cause them to be executed in the scope
    of that instance.

-   Class members are shared between all instances of a class. They can
    be accessed without an instance of the class, and class methods will
    execute in the scope of the class.

-   Static members are shared between all instances of a class and any
    sub-classes of it. They can be accessed without an instance of the
    class, and static methods will execute in the scope of the class.

The distinction between class and static members is not common to other object models. The essential difference is that a sub-class will recieve a copy of all its base classes' class members. This is opposed to static members, of which there is only one copy - sub classes access can their base classes' static members because they are automatically imported into the class' scope.




Invocation expressions
======================

-   invocation-expression:

    -   [ **yield** ] primary-expression **(** [ arguments ] **)**

    arguments:

    -   expression [ **,** arguments]

The expression can refer to any callable: a method, a delegate or a signal. The type of the expression depends upon the return type of the callable symbol. Each argument expression type must be compatible against the respective callable parameter type. If an argument is not provided for a parameter then:

1.  If the parameter has a default value, then that value will be used
    as argument.

2.  Otherwise an error occurs.

If the callable has an ellipsis parameter, then any number of arguments of any type can be provided past the ellipsis.

Delegates... See
[Delegates](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Delegates#)

Firing a signal is basically the same. See
[Classes/Signals](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#Signals)


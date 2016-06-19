

Method declaration
==================

The syntax for declaring a method changes slightly based on what sort of method is being declared. This section shows the form for a namespace method, Vala's closest equivalent to a global method in C. Many of the parts of the declaration are common to all types, so sections from here are referenced from class methods, interface methods, etc.

-   method-declaration:

    -   [ access-modifier ] return-type qualified-method-name ( [
        params-list ] ) [ **throws** error-list ] method-contracts **{**
        statement-list **}**

    return-type:

    -   type

        **void**

    qualified-method-name:

    -   [ qualified-namespace-name **.** ] method-name

    method-name:

    -   identifier

    params-list:

    -   parameter [ **,** params-list ]

    parameter:

    -   [ parameter-direction ] type identifier

    parameter-direction:

    -   **ref**

        **out**

    error-list:

    -   qualified-error-domain [ **,** error-list ]

    method-contracts:

    -   [ **requires** **(** expression **)** ] [ **ensures** **(**
        expression **)** ]

For more details see [Methods/Contract programming](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Methods#Contract_programming)
, and
[Errors](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Errors#)
.


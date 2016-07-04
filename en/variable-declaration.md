

Variable declaration
====================

Variable Declaration Statements define a local variable in current scope. The declaration includes a type, which signifies the variable will represent an instance of that type. Where the type can be inferred by the compiler, the type-name can be replaced with the literal `var`.

-   variable-declaration-statement:

    -   variable-declaration-with-explicit-type

    -   variable-declaration-with-explicit-type-and-initialiser

    -   variable-declaration-with-dynamic-type

    -   variable-declaration-with-dynamic-type-and-initialiser

    -   variable-declaration-with-type-inference
       

-   variable-declaration-with-explicit-type:

    -   type-name identifier **;**


-   variable-declaration-with-explicit-type-and-initialiser:

    -   type-name identifier **=** expression **;**


-   variable-declaration-with-dynamic-type:

    -   **dynamic** type-name identifier **;**


-   variable-declaration-with-dynamic-type-and-initialiser:

    -   **dynamic** type-name identifier **=** expression **;**


-   variable-declaration-with-type-inference:

    -   **var** identifier **=** expression **;**

The `dynamic` declaration allows a base type for a variable to be declared which allows subclasses to be assigned and used without needing to be cast. This feature is particularly useful when using Factory style patterns, such as those employed by GStreamer. At this stage, only dynamic properties are supported.

Type inference is possible in any case where the variable is immediately assigned to. The type chosen will always be the type of the assigned expression, as decided by the rules described at [Expressions](expressions.md). It is important to note that the type of the variable will be fixed after the first assignment. It will not change on assigning another value to the variable. If the variable should be created with a type other than that of the assigned expression, the expression should be wrapped with a cast expression (provided that the cast is valid).


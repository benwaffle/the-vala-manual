

Pointer expressions
===================

-   addressof-expression:

    -   **&** unary-expression

The "address of" expression evaluates to a pointer to the inner expression. Valid inner expressions are:

-   Variables (local variables, fields and parameters)

-   Element access whose container is an array or a pointer


-   pointer-indirection-expression:

    -   **\*** unary-expression

The pointer indirection evaluates to the value pointed to by the inner expression. The inner expression must be a valid pointer type and it must not be a pointer to a reference type. Pointer indirection to a type `SomeClass*` is not possible, for example.

-   pointer-member-access-expression:

    -   primary-expression **-\>** identifier

This expression evaluates to the value of the member identified by the identifier. The inner expression must be a valid pointer type and the member must be in the scope of the base type of the pointer type.


Member access
=============

To access members of another scope.

-   member-access-expression:

    -   [ primary-expression **.** ] identifier

If no inner expression is supplied, then the identifier will be looked up starting from the current scope (for example a local variable in a method). Otherwise, the scope of the inner expression will be used. The special identifier **this** (without inner expression) inside an instance method will refer to the instance of the type symbol (class, struct, enum, etc.).


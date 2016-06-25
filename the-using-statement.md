

The "using" statement
=====================

`using` statements can be used to avoid having to qualify names fully on a file-by-file basis. For all identifiers in the same file as the using statement, Vala will first try to resolve them following the usual rules (see [Concepts/Scope and naming](scope-and-naming.md)). If the identifier cannot be resolved in any scope, each namespace that is referenced in a `using` will be searched in turn.

-   using-statement:

    -   **using** namespace-list **;**

-   namespace-list:

    -   qualified-namespace-name [ **,** namespace-list ]

There can be any number of using statements in a Vala source file, but they must all appear outside any other declarations. Note that `using` is not like import statements in other languages - it does not load anything, it just allows for automatic searching of namespace scopes, in order to allow frugal code to be written.

Most code depends on members of the GLib namespace, and so many source files begin with:

    using GLib;

TODO: Include examples.

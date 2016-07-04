

Simple statements
=================

The Empty Statement does nothing, but is a valid statement nonetheless, and so can be used wherever a statement is required.

-   empty-statement:

    -   **;**

A Simple Statement consists of one a subset of expressions that are considered free-standing. Not all expressions are allowed, only those that potentially have a useful side effect - for example, arithmetic expressions cannot form simple statements on their own, but are allowed as part of an assignment expressions, which has a useful side effect.

-   simple-statement:

    -   statement-expression **;**

-   statement-expression:

    -   assigment-expression

    -   class-instantiation-expression

    -   struct instantiation-expression

    -   invocation-expression

A Statement Block allows several statements to be used in a context that would otherwise only allow one.

-   statement-block:

    -   **{** [ statement-list ] **}**

    statement-list:

    -   statement [ statement-list ]

Blocks create anonymous, transient scopes. For more details about scopes, see [Concepts/Scope and naming](scope-and-naming.md).


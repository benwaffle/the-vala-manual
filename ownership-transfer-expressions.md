

Ownership transfer expressions
==============================

-   ownership-transfer-expression:

    -   **(owned)** unary-expression

When an instance of a reference type is assigned to a variable or field, it is possible to request that the ownership of the instance is passed. The precise meaning of this depends on the reference type. For an explanation of ownership, see [Concepts/References and ownership](references-and-ownership.md). The identifier in this expression must refer to an instance of a reference type.

Note that similar syntax is used to define that a method parameter should take ownership of a value assigned to it. For this, see [Methods](methods.md).


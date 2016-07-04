

Type operations
===============

-   is-expression:

    -   shift-expression **is** type-name

Performs a runtime type check on the instance resulting from evaluating the nested expression. If the instance is an instance of the type described (a class or interface for example) the overall expression evaluates to true.

Casting:

-   cast-expression:

    -   **(!)** unary-expression

    -   **(** type-name **)** unary-expression

A cast expression returns the instance created in the nested expression as an instance of the type described. If the nested expression evaluates to an instance of a type that is not also an instance of the given type, the expression is not valid. If you are not sure whether the cast is valid, instead use an "as" expression.

-   as-expression:

    -   shift-expression **as** type-name

An "as" expression combines an "is" expression and a cast operation, with the latter depending on the former. If the nested expression evaluates to an instance of the given type, then a cast is performed and the expression evaluates to the result of the nested expression cast as the given type. Otherwise, the result is null.

-   sizeof-expression:

    -   **sizeof (** type-name **)**


-   typeof-expression:

    -   **typeof (** type-name **)**

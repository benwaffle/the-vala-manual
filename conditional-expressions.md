

Conditional expressions
=======================

Allow a conditional in a single expression.

-   conditional-expression:

    -   boolean-expression [ **?** conditional-true-clause **:** conditional-false-clause ]

-   boolean-expression:

    -   coalescing-expression

-   conditional-true-clause:

    -   expression


-   conditional-false-clause

    -   expression

First boolean-expression is evaluated. If true, then the conditional-true-clause is evaluated, and its result is the result of the conditional expression. If the boolean expression evaluates to false, then the conditional-false-clause is evaluated, and its result becomes the result of the conditional expression.


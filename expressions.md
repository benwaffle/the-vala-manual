# Expressions

Expressions are short pieces of code that define an action that should be taken when they are reached during a program's execution. Such an operation can be arithmetical, calling a method, instantiating a type,
and so on. All expressions evaluate to a single value of a particular type - this value can then be used in another expression, either by combing the expressions together, or by assigning the value to an identifier.

When expressions are combined together (e.g. add two numbers, then multiply the result by another: 5 + 4 \* 3), then the order in which the sub-expressions are evaluated becomes significant. Parentheses are used to mark out which expressions should be nested within others, e.g. (5 +
4) \* 3 implies the addition expression is nested inside the multiplication expression, and so must be evaluated first.

When identifiers are used in expressions they evaluate to their value,
except when used in assignment. The left handed side of an assignment are a special case of expressions where an identifier is not considered an expression in itself and is therefore not evaluated. Some operations combine assignment with another operation (e.g. increment operations,)
in which cases an identifier can be thought of as an expression initially, and then just an identifier for assignment after the overall expression has been evaluated.

-   primary-expression:

    -   literal

        template

        member-access-expression

        pointer-member-access-expression

        element-access-expression

        postfix-expression

        class-instantiation-expression

        array-instantiation-expression

        struct-instantiation-expression

        invocation-expression

        sizeof-expression

        typeof-expression

    unary-expression:

    -   primary-expression

        sign-expression

        logical-not-expression

        bitwise-not-expression

        prefix-expression

        ownership-transfer-expression

        cast-expression

        pointer-expression

    expression:

    -   conditional-expression

        assignment-expression

        lambda-expression
<div id="arithmetic-operations" class="section level1">

Arithmetic operations
=====================

Binary operators, taking one argument on each side. Each argument is an
expression returning an appropriate type.

Applicable, unless said otherwise, where both operands evaluate to
numeric types (integer or floating point).

Where at least one operand is a of floating point type, the result will
be the same type as the largest floating point type involved. Where both
operands are of integer types, the result will have the same type as the
largest of the integer types involved.

Addition/Subtraction:

-   additive-expression:

    -   multiplicative-expression

        multiplicative-expression **+** multiplicative-expression

        multiplicative-expression **-** multiplicative-expression

    sign-expression:

    -   **+** unary-expression

        **-** unary-expression

Adds/Subtracts the second argument to/from the first. Negations is
equivalent to subtraction the operand from 0.

Overflow?

Multiplication/Division:

-   multiplicative-expression:

    -   unary-expression

        unary-expression **\*** unary-expression

        unary-expression **/** unary-expression

        unary-expression **%** unary-expression

Multiplies/divides the first argument by the second.

If both operands are of integer types, then the result will be the
quotient only of the calculation (equivalent to the precise answer
rounded down to an integer value.) If either operand is of a floating
point type, then the result will be as precise as possible within the
boundaries of the result type (which is worked out from the basic
arithmetic type rules.)

</div>

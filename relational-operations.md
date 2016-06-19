<div id="relational-operations" class="section level1">

Relational operations
=====================

Result in a value of bool type.

Applicable for comparing two instances of any numeric type, or two
instances of string type. Where numeric with at least one floating point
type instance, operands are both converted to the largest floating point
type involved. Where both operands are of integer type, both are
converted to the largest integer type involved. When both are strings,
they are lexically compared somehow.

-   equality-expression:

    -   relational-expression

        relational-expression **==** relational-expression

        relational-expression **!=** relational-expression

    relational-expression:

    -   shift-expression

        shift-expression **\<** relational-expression

        shift-expression **\<=** relational-expression

        shift-expression **\>** relational-expression

        shift-expression **\>=** relational-expression

        is-expression

        as-expression

</div>

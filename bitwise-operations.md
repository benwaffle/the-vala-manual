<div id="bitwise-operations" class="section level1">

Bitwise operations
==================

All only applicable to integer types.

-   bitwise-or-expression:

    -   bitwise-xor-expression **|** bitwise-xor-expression

    bitwise-xor-expression:

    -   bitwise-and-expression **&** bitwise-and-expression

    bitwise-and-expression:

    -   equality-expression **&** equality-expression

    bitwise-not-expression:

    -   **\~** expression

Documentation

-   shift-expression:

    -   additive-expression **\<\<** additive-expression

        additive-expression **\>\>** additive-expression

Shifts the bits of the left argument left/right by the number
represented by the second argument.

Undefined for shifting further than data size, e.g. with a 32 bit
integer...

Documentation

</div>

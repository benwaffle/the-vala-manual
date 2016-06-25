

Flag operations
===============

Flag types are a variation on enumerated types, in which any number of flag values can be combined in a single instance. There are operations available to combine several values in an instance, and to find out which values are represented.

-   flag-combination-expression:

    -   expression **|** expression

Where both expressions evaluate to instances of the same flag type, the result of this expression is a new instance of the flag type in which all values represented by either operand are represented.

-   flag-recombination-expression:

    -   expression **\^** expression

Where both expressions evaluate to instances of the same flag type, the result of this expression is a new instance of the flag type in which all values represented by exactly one of the operands are represented.

-   flag-separation-expression:

    -   expression **&** expression

Where both expressions evaluate to instances of the same flag type, the result of this expression is a new instance of the flag type in which all values represented by both operands are represented.

-   flag-in-expression:

    -   expression **in** expression

Where both expressions evaluate to instances of the same flag type, the result of this expression is a boolean. The result will be true if the left-handed flag is set into the right-handed flags.

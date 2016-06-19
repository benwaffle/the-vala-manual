

Array instantiation
===================

This expression will create an array of the given size. The second approach shown below is a shorthand to the first one.

-   array-instantiation-expression:

    -   **new** type-name **[\*\* sizes \*\*]** [ **{** [ initializer ]
        **}** ]

        **{** initializer **}**

    sizes:

    -   expression [ **,** sizes ]

    initializer:

    -   expression [ **,** initializer ]

Sizes expressions must evaluate either to an integer type or an enum value. Initializer expressions type must be compatible with the array element type.


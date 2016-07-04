

Directives syntax
=================

All preprocessor directives start with a hash ( **\#** ), except for the first line of a file starting with **\#!** (used for Vala scripts).

-   vala-code:

    -   [ any vala code ] [ pp-condition ] [ any vala code ]


-   pp-condition:

    -   **\#if** pp-expression vala-code [ pp-elif ] [ pp-else ] **\#endif**


-   pp-elif:

    -   **\#elif** pp-expression vala-code [ pp-elif ]


-   pp-else:

    -   **\#else** vala-code


-   pp-expression:

    -   pp-or-expression


-   pp-or-expression:

    -   pp-and-expression [ **||** pp-and-expression ]


-   pp-and-expression:

    -   pp-binary-expression [ **&&** pp-binary-expression ]


-   pp-binary-expression:

    -   pp-equality-expression

    -   pp-inequality-expression


-   pp-equality-expression:

    -   pp-unary-expression [ **==** pp-unary-expression ]


-   pp-inequality-expression:

    -   pp-unary-expression [ **!=** pp-unary-expression ]


-   pp-unary-expression:

    -   pp-negation-expression

    -   pp-primary-expression


-   pp-negation-expression:

    -   **!** pp-unary-expression


-   pp-primary-expression:

    -   pp-symbol

    -   **(** pp-expression **)**

    -   **true**

    -   **false**

-   pp-symbol:

    -   identifier

The semantics of the preprocessor are very simple: if the condition is true then the Vala code surrounded by the preprocessor will be parsed, otherwise it will be ignored. A symbol evaluates to **true** if it is defined at compile-time. If a symbol in a preprocessor directive is not defined, it evaluates to **false** .

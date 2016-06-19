

Syntax
======

Metadata information for each symbol must provided on different lines:

-   rule:

    -   pattern [ arguments ] [ `newline` relative-rules ] `newline`

    relative-rules:

    -   **.** pattern [ arguments ] [ `newline` relative-rules ]

    pattern:

    -   `glob-style-pattern` [ **\#** selector ] [ **.** pattern ]

    arguments:

    -   `identifier` [ **=** expression ] [ arguments ]

    expression:

    -   **null**

        **true**

        **false**

        **-** expression

        integer-literal

        real-literal

        string-literal

        symbol

    symbol:

    -   identifier [ **.** identifier ]

<!-- -->

-   Patterns are tied to the GIR tree: if a class `FooBar` contains a method `baz_method` then it can be referenced in the metadata as
    `FooBar.baz_method` .

-   Selectors are used to specify a particular element name of the GIR tree, for example `FooBar.baz_method#method` will only select method elements whose name is baz\_method. Useful to solve name collisions.

-   Given a namespace named `Foo` a special pattern `Foo` is available for setting general arguments.

-   If a GIR symbol matches multiple rules then all of them will be applied: if there are clashes among arguments, last written rules in the file take precedence.

-   If the expression for an argument is not provided, it's treated as
    **true** by default.

-   A *relative rule* is relative to the nearest preceding *absolute rule* . Metadata must contain at least one absolute rule. It's not possible to make a rule relative to another relative rule.


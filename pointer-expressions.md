<div id="pointer-expressions" class="section level1">

Pointer expressions
===================

-   addressof-expression:

    -   **&** unary-expression

The "address of" expression evaluates to a pointer to the inner
expression. Valid inner expressions are:

-   Variables (local variables, fields and parameters)

-   Element access whose container is an array or a pointer

    pointer-indirection-expression:

    -   **\*** unary-expression

The pointer indirection evaluates to the value pointed to by the inner
expression. The inner expression must be a valid pointer type and it
must not be a pointer to a reference type (for example pointer
indirection to a type `SomeClass*` is not possible).

-   pointer-member-access-expression:

    -   primary-expression **-\>** identifier

This expression evaluates to the value of the member identified by the
identifier. The inner expression must be a valid pointer type and the
member must be in the scope of the base type of the pointer type.

Back to [Vala Reference
Manual](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual#)

<div id="statements" class="section level2">

Statements
----------

Statements define the path of execution within methods and similar
constructions. They combine expressions together with structures for
choosing between different code paths, repeating code sections, etc.

-   statement:

    -   empty-statement

        simple-statement

        statement-block

        variable-declaration-statement

        if-statement

        switch-statement

        while-statement

        do-statement

        for-statement

        foreach-statement

        return-statement

        throw-statement

        try-statement

        lock-statement

    embedded-statement:

    -   statement

</div>

</div>
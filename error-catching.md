

Error catching
==============

The syntax of the try statement:

-   try-statement:

    -   **try** statement-block catch-clauses

        **try** statement-block [catch-clauses] finally-clause

    catch-clauses:

    -   [ specific-catch-clauses ] general-catch-clause

    specific-catch-clauses:

    -   specific-catch-clause

        [ specific-catch-clauses ]

    specific-catch-clause:

    -   **catch** **(** qualified-error-type identifier **)**
        statement-block

    general-catch-clause:

    -   **catch** statement-block

    finally-clause:

    -   **finally** statement-block

In the statement block scope of each catch clause, the error is assigned to a variable with the identifier given.


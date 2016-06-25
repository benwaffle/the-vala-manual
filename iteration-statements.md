

Iteration statements
====================

Iteration statements are used to execute statements multiple times based on certain conditions. Iteration Statements contain loop embedded statements - a superset of embedded statements which adds statements for manipulating the iteration.

-   loop-embedded-statement:

    -   loop-embedded-statement-block

    -   embedded-statement

    -   break-statement

    -   continue-statement

-   loop-embedded-statement-block:

    -   **{** [ loop-embedded-statement-list ] **}**

-   loop-embedded-statement-list:

    -   loop-embedded-statement [ loop-embedded-statement-list ]

Both break and continue statement are types of jump statement, described in [Statements/Jump statements](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Statements#Jump_statements).

The while statement conditionally executes an embedded statement zero or more times. When the while statement is reached, the boolean expression is executed. If the boolean value is true, the embedded statement is executed and execution returns to the while statement. If the boolean value is false, execution continues after the while statement.

-   while-statement:

    -   **while** **(** boolean-expression **)** loop-embedded-statement

The do statement conditionally executes an embedded statement one or more times. First the embedded statement is executed, and then the boolean expression is evaluated. If the boolean value is true, execution returns to the do statement. If the boolean value is false, execution continues after the do statement.

-   do-statement:

    -   **do** loop-embedded-statement **while** **(** boolean-expression **)** **;**

The for statement first evaluates a sequence of initialization expressions, then repeatedly executes an embedded statement. At the start of each iteration a boolean expression is evaluated, with a true value leading the execution of the embedded statement, a false value leading to execution passing to the first statement following the do statement. After each iteration a sequence of iteration expressions are evaluated. Executing this type of statement creates a new transient scope, in which any variables declared in the initializer are created.

-   for-statement:

    -   **for** **(** [ for-initializer ] **;** [ for-condition ] **;** [ for-iterator ] **)** loop-embedded-statement

-   for-initializer:

    -   variable-declaration [ **,** expression-list ]

-   for-condition:

    -   boolean-expression

    for-iterator:

    -   expression-list

The foreach statement enumerates the elements of a collection, executing an embedded statement for each element of the collection. Each element in turn is assigned to a variable with the given identifier and the embedded statement is executed. Executing this type of statement creates a new transient scope in which the variable representing the collection element exists.

-   foreach-statement:

    -   **foreach** **(** type identifier **in** expression **)**
        loop-embedded-statement

Foreach Statements are able to iterate over arrays and any class that implements the Gee.Iterable interface. This may change in future if an Iterable interface is incorporated into GLib.


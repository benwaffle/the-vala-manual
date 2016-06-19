

Jump statements
===============

Jump statements move execution to an arbitary point, dependent on the type of statement and its location. In any of these cases any transient scopes are ended appropriately: [Concepts/Scope and naming](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#Scope_and_naming)
and [Statements/Simple statements](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Statements#Simple_statements)
.

A break statement moves execution to the first statement after the nearest enclosing while, do, for, or foreach statement.

-   break-statement:

    -   **break** **;**

A continue statement immediately moves execution the nearest enclosing while, do, for, or foreach statement.

-   continue-statement:

    -   **continue** **;**

The return statement ends the execution of a method, and therefore completes the invocation of the method. The invocation expression has then been fully evaluated, and takes on the value of the expression in the return statement if there is one.

-   return-statement:

    -   **return** [ expression ] **;**

The throw statement throws an exception.

-   throw-statement:

    -   **throw** expression **;**


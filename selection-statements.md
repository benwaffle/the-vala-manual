

Selection statements
====================

The If Statement decides whether to execute a given statement based on the value of a boolean expression. There are two possible extensions to this model:

An else clause declares that a given statement should be run if-and-only-if the condition in the if statement fails.

Any number of "else if" clauses may appear between the "if" statement and its "else" clause (if there is one). These are equivalent to:

FIXME: This doesn't work.

In simple terms, the program will test the conditions of the if statement and its "else if" clauses in turn, executing the statement belonging to the first that succeeds, or running the else clause if every condition fails.

-   if-statement:

    -   **if** **(** boolean-expression **)** embedded-statement [ elseif-clauses ] [ **else** embedded-statement ]


-   elseif-clauses:

    -   elseif-clause

    -   [ elseif-clauses ]

-   elseif-clause:

    -   **else if** **(** boolean-expression **)** embedded-statement

The switch statement decides which of a set of statements to execute based on the value of an expression. A switch statement will lead to the execution of one or zero statements. The choice is made by:

-   switch-statement:

    -   **switch** **(** expression **)** **{** [ case-clauses ] [ default-clause ] **}**

-   case-clauses:

    -   case-clause

    -   [ case-clauses ]

-   case-clause:

    -   **case** literal-expression **:** embedded-statement

-   default-clause:

    -   **default** **:** embedded-statement

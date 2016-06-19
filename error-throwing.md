

Error throwing
==============

Throwing an error is done with the following syntax:

-   throw-statement:

    -   **throw** error-description **;**

    error-description:

    -   identifier

        error-creation-expression

    error-creation-expression:

    -   **new** qualified-error-type **(** message-expression **)**

    qualified-error-type:

    -   qualified-error-domain **.** error-type

    qualified-error-domain:

    -   [ qualified-namespace-name **.** ] error-domain-name

That is, throw an error that has already been created and can be identified by a name, or a new error created with a textual description.
The message-expression is any expression that evaluates to a instace of the string type.


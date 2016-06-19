

Constants
=========

Constants are similar to variables but can only be assigned to once. It is therefore required that the expression that initialises the constant be executable at the time the constant comes into scope. For namespaces this means that the expressions must be evaluable at the beginning of the application's execution.

-   constant-declaration:

    -   [ access-modifier ] **const** qualified-type-name constant-name
        **=** expression ;

    constant-name:

    -   identifier


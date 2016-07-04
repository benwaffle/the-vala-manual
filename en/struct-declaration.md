

Struct declaration
==================

-   struct-declaration:

    -   [ access-modifier ] **struct** qualified-struct-name [ **:** super-struct ] **{** [ struct-members ] **}**


-   qualified-struct-name:

    -   [ qualified-namespace-name **.** ] struct-name


-   struct-name:

    -   identifier

-   struct-members:

    -   struct-member [ struct-members ]


-   struct-member:

    -   struct-creation-method-declaration:

    -   struct-field-declaration

    -   struct-constant-declaration

    -   struct-method-declaration

If a super-struct is given, the struct-name becomes an alias for that struct.


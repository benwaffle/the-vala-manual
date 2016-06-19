

Interface declaration
=====================

-   interface-declaration:

    -   [ access-modifier ] **interface** qualified-interface-name [
        inheritance-list ] **{** [ interface-members ] **}**

    qualified-interface-name:

    -   [ qualified-namespace-name **.** ] interface-name

    interface-name:

    -   identifier

    inheritance-list:

    -   **:** prerequisite-classes-and-interfaces

    prerequisite-classes-and-interfaces:

    -   qualified-class-name [ **,**
        prerequisite-classes-and-interfaces]

        qualified-interface-name [ **,**
        prerequisite-classes-and-interfaces ]

    interface-members:

    -   interface-member [ interface-members ]

    interface-member:

    -   interface-constant-declaration

        interface-delegate-declaration

        interface-enum-declaration

        interface-instance-member

        interface-static-member

        interface-inner-class-declaration

        abstract-method-declaration

    interface-instance-member:

    -   interface-instance-method-declaration

        interface-instance-abstract-method-declaration

        interface-instance-property-declaration

        interface-instance-signal-declaration

    interface-static-member:

    -   interface-static-field-declaration

        interface-static-method-declaration


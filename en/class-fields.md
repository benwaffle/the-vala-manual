

Class fields
============

Fields act as variable with a scope of either the class or a particular instance, and therefore have names and types in the same way. Basic declarations are as:

-   class-instance-field-declaration:

    -   [ class-member-visibility-modifier ] qualified-type-name field-name [ **=** expression ] ;

-   class-class-field-declaration:

    -   [ class-member-visibility-modifier ] **class** qualified-type-name field-name [ **=** expression ] ;

-   class-static-field-declaration:

    -   [ class-member-visibility-modifier ] **static** qualified-type-name field-name [ **=** expression ] ;

Initial values are optional. FIXME: how much calculation can be done here? what are the defaults?

> **Note**
>
> Initial values are only allowed in GObject derived classes.

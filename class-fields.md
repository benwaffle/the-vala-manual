<div id="class-fields" class="section level1">

Class fields
============

Fields act as variable with a scope of either the class or a particular
instance, and therefore have names and types in the same way. Basic
declarations are as:

-   class-instance-field-declaration:

    -   [ class-member-visibility-modifier ] qualified-type-name
        field-name [ **=** expression ] ;

    class-class-field-declaration:

    -   [ class-member-visibility-modifier ] **class**
        qualified-type-name field-name [ **=** expression ] ;

    class-static-field-declaration:

    -   [ class-member-visibility-modifier ] **static**
        qualified-type-name field-name [ **=** expression ] ;

Initial values are optional. FIXME: how much calculation can be done
here? what are the defaults?

> **Note**
>
> -   **Note** Initial values are only allowed in GObject derived
>     classes.
>
> Class constants
> ===============

Constants defined in a class are basically the same as those defined in
a namespace. The only difference is the scope and the choice of
visibilities available.

-   class-constant-declaration:

    -   [ class-member-visibility-modifier ] **const**
        qualified-type-name constant-name **=** expression ;

</div>

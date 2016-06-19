<div id="generics-declaration" class="section level1">

Generics declaration
====================

Some of the syntax could be best placed in the class/interface/struct
pages, but that might overcomplicate them...

In class declaration - In struct declaration - In interface
declaration - In base class declaration - In implemented interfaces
declaration - In prerequesite class/interface declaration.

Declaration with type parameters introduces new types into that scope,
identified by names given in declaration, e.g. T.

-   qualified-type-name-with-generic:

    -   qualified-class-name-with-generic

        qualified-interface-name-with-generic

        qualified-struct-name-with-generic

    qualified-class-name-with-generic:

    -   [ qualified-namespace-name **.** ] class-name type-parameters

    qualified-interface-name-with-generic:

    -   [ qualified-namespace-name **.** ] interface-name
        type-parameters

    qualified-struct-name-with-generic:

    -   [ qualified-namespace-name **.** ] struct-name type-parameters

    type-parameters:

    -   **\<** generic-clause **\>**

    generic-clause:

    -   type-identifier [ **,** generic-clause ]

        qualified-type-name [ **,** generic-clause ]

    type-identifier:

    -   identifier

type-identifier will be the type-name for the parameterised type.

Deal is: in the class/interface/struct sections, replace
qualified-\*-name with qualified-\*-name-with-generic.

</div>

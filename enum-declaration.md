<div id="enum-declaration" class="section level1">

Enum declaration
================

-   enum-declaration:

    -   [ access-modifier ] **enum** qualified-enum-name **{** [
        enum-members ] **}**

    qualified-enum-name:

    -   [ qualified-namespace-name **.** ] enum-name

    enum-name:

    -   identifier

    enum-members:

    -   [ enum-values ] [ **;** enum-methods ]

    enum-values:

    -   enum-value [ **,** enum-values ]

    enum-value:

    -   enum-value-name [ **=** expression ]

    enum-value-name:

    -   identifier

    enum-methods:

    -   enum-method [ enum-methods ]

    enum-method:

    -   method-declaration

</div>

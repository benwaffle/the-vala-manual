

Class member visibility
=======================

All class members have a visibility. This defines whether the member is visible to code in different locations. Visibility is declared using the follow mutually exclusive modifiers:

-   class-member-visibility-modifier:

    -   **public**

    -   **private**

    -   **protected**

    -   **internal**

-   "public" asserts that the member should be visible to any code.

-   "private" asserts that the member will only be visible to code that is within this class declaration.

-   "protected" asserts that the member will be visible to any code within this class, and also to any code that is in a subclass of this class.

-   "internal" asserts that the member will be visible only to code within the same "package".


> **C Note**
>
> A field or method's protected status cannot be enforced in the C
> translation of a Vala library.


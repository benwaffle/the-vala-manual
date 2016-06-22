

Element access
==============

-   element-access-expression:

    -   container **[\*\* indexes \*\*]**

-   container:

    -   expression

-   indexes:

    -   expression [ **,** indexes ]

Element access can be used for:

-   Accessing an element of a container at the given indexes

-   Assigning an element to a container at the given indexes. In this case the element access expression is the left handed side of an assignment.

Element access can be used on strings, arrays and types that have **get** and/or **set** methods.

-   On strings you can only access characters, it's not possible to assign any value to an element.

-   On arrays, it's possible to both access an element or assign to an element. The type of the element access expression is the same as the array element type.

Element access can also be used with complex types (such as class, struct, etc.) as containers:

-   If a **get** method exists accepting at least one argument and returning a value, then indexes will be used as arguments and the return value as element.

-   If a **set** method exists accepting at least two arguments and returns **void** , then indexes will be used as arguments and the assigned value as last argument..

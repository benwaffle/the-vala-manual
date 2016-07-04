# Types

A "type", loosely described, is just an abstract set of 0 or more data fields. A type may be instantiated by creating an entity that contains values that map to the fields of the type. In Vala, a type generally consists of:

-   A type name, which is used in various contexts in Vala code to signify an instance of the type.

-   A data structure that defines how to represent an instance of the type in memory.

-   A set of methods that can be called on an instance of the type.

These elements are combined as the definition of the type. The definition is given to Vala in the form of a declaration, for example a class declaration.

Vala supports three kinds of data types: value types, reference types,
and meta types. Value types include simple types (e.g. char, int, and float), enum types, and struct types. Reference types include object types, array types, delegate types, and error types. Type parameters are parameters used in generic types.

Value types differ from reference types in that there is only ever one variable or field that refers to each instance, whereas variables or fields of the reference types store references to data which can also be referred to by other variable or fields. When two variables or fields of a reference type reference the same data, changes made using one identifier are visible when using the other. This is not possible with value types.

Meta types are created automatically from other types, and so may have either reference or value type semantics.

-   type:

    -   value-type

    -   reference-type

    -   meta-type

-   meta-type:

    -   parameterised-type

    -   nullable-type

    -   pointer-type

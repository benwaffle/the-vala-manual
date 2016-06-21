# Reference types

Instances of reference types are always stored on the heap. Variables of reference types contain references to the instances, rather than the instances themselves. Assigning an instance of a reference type to a variable or field will not make a copy of the data, only a reference to it. This means that both variables will refer to the same data. Changes made to that data using one of the references will be visible when using the other.

Instances of any reference type can be assigned a variable that is declared "weak". This implies that the variable must not be known to the type instance. A reference counted type does not increase its reference count after being assigned to a weak variable. A weak variable cannot take ownership of an instance.

-   reference-type:

    -   classed-type

    -   array-type

    -   delegate-type

    -   error-type

    -   **string**

-   classed-type:

    -   simple-classed-type

    -   type-instance-classed-type

    -   object-classed-type

    - simple-classed-type:

    -   user-defined-simple-classed-type

-   type-instance-classed-type:

    -   user-defined-type-instance-classed-type


-   object-classed-type:

    -   user-defined-object-classed-type


-   array-type:

    -   non-array-type **[]**

    -   non-array-type **[** dimension-separators **]**

-   non-array-type:

    -   value-type

    -   classed-type

    -   delegate-type

    -   error-type

-   dimension-separators:

    -   **,**

    -   dimension-separators **,**

-   delegate-type:

    -   user-defined-delegate-type

-   error-type:

    -   user-defined-error-type

#### Classed types

A class definition introduces a new reference type - this is the most common way of creating a new type in Vala. Classes are a very powerful mechanism, as they have features such as polymorphism and inheritance.

Full discussion of classes is found at
[Classes](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Classes#).

Most classed types in Vala are reference counted. This means that every time a classed type instance is assigned to a variable or field, not only is the reference copied, but the instance also records that another reference to it has been created. When a field or variable goes out of scope, the fact that a reference to the instance has been removed is also recorded. This means that a classed type instance can be automatically removed from memory when it is no longer needed. The only classed types that are not reference counted are compact classes..
Memory management is discussed at [Overview/Memory management](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Overview#Memory_management)
. If the instance is not of a reference counted type, then the ownership must be explicitly transferred using the \# operator - this will cause the original variable to become invalid. When a classed-type instance is passed to a method, the same rules apply. The types of classes available are discussed at [Classes/Types of class](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Classes#Types_of_class)
.

#### Array types

TODO: Check correctness.

An array is a data structure that can contains zero or more elements of the same type, up to a limit defined by the type. An array may have multiple dimensions; for each possible set of dimensions a new type is implied, but there is a meta type available that describes an array of any size with the same number of dimensions, i.e. int[1] is not the same type as int[2], while int[] is the same type as either.

See [Expressions/Array instantiation](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Expressions#Array_instantiation)
for how to instantiate an array type.

#### Delegate types

A delegate is a data structure that refers to a method. A method executes in a given scope which is also stored, meaning that for instance methods a delegate will contain also a reference to the instance.

Delegates are technically a referenced type, but since methods are immutable, this distinction is less important than for other types.
Assigning a delegate to a variable or field cannot copy the method indicated, and no delegate is able to change the method in any way.

See
[Delegates](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Delegates#)
for full documentation.

#### Error Types

Instances of error types represent recoverable runtime errors. All errors are described using error domains, a type of enumerated value,
but errors themselves are not enumerated types. Errors are discussed in detail in several sections of this documentation, see:
[Errors](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Errors#)
, [Enumerated types (Enums)/Error domains](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Enumerated%20types%20%28Enums%29#Error_domains)
and
[Methods](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Methods#)
.

#### Strings

Vala has built in support for Unicode strings, via the fundamental string type. This is the only fundamental type that is a reference type.
Like other fundamental types, it can be instantiated with a literal expression ( [Expressions/Literal expressions](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Expressions#Literal_expressions)
.) Strings are UTF-8 encoded, the same as Vala source files, which means that they cannot be accessed like character arrays in C - each Unicode character is not guaranteed to be stored in just one byte. Instead the string fundamental struct type (which all strings are instances of)
provides access methods along with other tools.

While strings are technically a reference type, they have the same default copy semantics as structs - the data is copied whenever a string value is assigned to a variable or field, but only a reference is passed as a parameter to a method. This is required because strings are not reference counted, and so the only way for a variable or field to be able to take ownership of a string is by being assigned a copy of the string. To avoid this behaviour, string values can be assigned to weak references (in such a case no copy is made).

The concept of ownership is very important in understanding string semantics. For more details see [Concepts/References and ownership](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Concepts#References_and_ownership).
<div id="value-types-1" class="section level1">

Value types
===========

Instances of value types are stored directly in variables or fields that
represent them. Whenever a value type instance is assigned to another
variable or field, the default action is to duplicate the value, such
that each identifier refers to a unique copy of the data, over which it
has ownership. When a value type is instantiated in a method, the
instance is created on the stack.

-   value-type:

    -   fundamental-struct-type

        user-defined-struct-type

        enumerated-type

    fundamental-struct-type:

    -   integral-type

        floating-point-type

        **bool**

    integral-type:

    -   **char**

        **uchar**

        **short**

        **ushort**

        **int**

        **uint**

        **long**

        **ulong**

        **size\_t**

        **ssize\_t**

        **int8**

        **uint8**

        **int16**

        **uint16**

        **int32**

        **uint32**

        **int64**

        **uint64**

        **unichar**

    floating-point-type:

    -   **float**

        **double**

Where a literal is indicated, this means the actual type name of a built
in struct type is given. The definition of these types is included in
Vala, so these types are always available.

<div id="struct-types" class="section level2">

Struct types
------------

A struct type is one that provides just a data structure and some
methods that act upon it. Structs are not polymorphic, and cannot have
advanced features such as signals or properties. See
[Structs](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Structs#)
for documentation on how to define structs and more details about them.
See [Expressions/Struct
instantiation](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Expressions#Struct_instantiation)
for how to instantiate structs.

Each variable or field to which a struct stype instance is assigned
gains a copy of the data, over which it has ownership. However, when a
struct type instance is passed to a method, a copy is not made. Instead
a reference to the instance is passed. This behaviour can be changed by
declaring the struct to be a simple type.

</div>

<div id="fundamental-types" class="section level2">

Fundamental types
-----------------

In Vala, the fundamental types are defined as struct types whose data
structure is known internally to Vala. They have one anonymous field,
which is automatically accessed when required. All fundamental value
types are defined as simple types, and so whenever the instance is
assigned to a variable or field or passed as a function parameter, a
copy of the data is made.

The fundamental value types fall into one of three categories: the
boolean type, integral types, and floating point types.

</div>

<div id="integral-types" class="section level2">

Integral types
--------------

Integral types can contain only integers. They are either signed or
unsigned, each of which is considered a different type, though it is
possible to cast between them when needed.

Some types define exactly how many bits of storage are used to represent
the integer, others depend of the environment. long, int short map to C
data types and therefore depend on the machine architecture. char is 1
byte. unichar is 4 bytes, i.e. large enough to store any UTF-8
character.

All these types can be instantiated using a literal expression, see
[Expressions/Literal
expressions](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Expressions#Literal_expressions)
.

</div>

<div id="floating-point-types" class="section level2">

Floating point types
--------------------

Floating point types contain real floating point numbers in a fixed
number of bits (see IEEE 754).

All these types can be instantiated using a literal expression, see
[Expressions/Literal
expressions](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Expressions#Literal_expressions)
.

</div>

<div id="the-bool-type" class="section level2">

The bool type
-------------

Can have values of true of false. Although there are only two values
that a bool instance can take, this is not an enumerated type. Each
instance is unique and will be copied when required, the same as for the
other fundamental value types.

This type can be instantiated using literal expressions, see
[Expressions/Literal
expressions](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Expressions#Literal_expressions)
.

</div>

<div id="enumerated-types" class="section level2">

Enumerated types
----------------

An enumerated type is one in which all possible values that instances of
the type can hold are declared with the type. In Vala enumerated types
are real types, and will not be implicitly converted. It is possible to
explicitly cast between enumerated types, but this is not generally
advisable. When writing new code in Vala, don't rely on being able to
cast in this way.

A variation on an enumerated type is a flag type. This represents a set
of flags, any number of which can be combined in one instance of the
flag type, in the same fashion as a bitfield in C.

See [Enumerated types
(Enums)](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Enumerated%20types%20%28Enums%29#)
for documentation on defining and using enumerated types.

</div>

</div>

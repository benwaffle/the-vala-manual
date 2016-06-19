<div id="pointer-types-1" class="section level1">

Pointer types
=============

The name of a type can be used to implicitly create a pointer type
related to that type. The value of a variable declared as being of type
T\* represents the memory address of an instance of type T. The instance
is never made aware that its address has been recorded, and so cannot
record the fact that it is referred to in this way.

Instances of any type can be assigned to a variable that is declared to
be a pointer to an instance of that type. For referenced types, direct
assignment is allowed in either direction. For value types the
pointer-to operator "&" is required to assign to a pointer, and the
pointer-indirection operator "\*" is used to access the instance pointed
to. See [Expressions/Pointer
expressions](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Expressions#Pointer_expressions)
.

The `void*` type represents a pointer to an unknown type. As the
referent type is unknown, the indirection operator cannot be applied to
a pointer of type `void*` , nor can any arithmetic be performed on such
a pointer. However, a pointer of type `void*` can be cast to any other
pointer type (and vice-versa) and compared to values of other pointer
types. See [Expressions/Type
operations](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Projects/Vala/Manual/Expressions#Type_operations)
.

A pointer type itself has value type semantics.

</div>

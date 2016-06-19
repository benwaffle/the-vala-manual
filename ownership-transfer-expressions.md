<div id="ownership-transfer-expressions" class="section level1">

Ownership transfer expressions
==============================

-   ownership-transfer-expression:

    -   **(owned)** unary-expression

When an instance of a reference type is assigned to a variable or field,
it is possible to request that the ownership of the instance is passed
to the new field or variable. The precise meaning of this depends on the
reference type, for an explanation of ownership, see
[Concepts/References and
ownership](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#References_and_ownership)
. The identifier in this expression must refer to an instance of a
reference type.

Note that similar syntax is used to define that a method parameter
should take ownership of a value assigned to it. For this, see
[Methods](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Methods#)
.

</div>



Literal expressions
===================

Each literal expression instantiates its respective type with the value given.

Integer types... -?[:digit:]+

Floating point types... -?[:digit:]+(.[:digit:]+)?

Strings... "[\^"\\n]\*". """.\*"""

Booleans... true|false

A final literal expression is `null` . This expression evaluates to a non-typed data instance, which is a legal value for any nullable type
(see [Types/Nullable types](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Types#Nullable_types)
.)


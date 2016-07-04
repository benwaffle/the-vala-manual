# Type conversions

There are two types if type conversions possible in Vala, implicit conversions and explicit casts. In expressions, Vala will often convert fundamental types in order to make calculations possible. When the default conversion is not what you require, you can cast explicitly so that all operands are of compatible types. See [Expressions](expressions.md) for details of automatic conversions.

Vala will also automatically perform conversions related to polymorphism where the required cast is unambiguous and can be inferred from the context. This allows you to use a classed-type instance when an instance of any of its superclasses or implemented interfaces is required. Vala will never automatically cast to a subtype, as this must be done explicitly. See [Concepts/Object oriented programming](object_oriented_programming.md), see [Classes](classes.md).

For explicit casting expressions, see [Expressions/Type operations](type-operations.md).

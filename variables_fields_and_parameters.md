# Variables, fields and parameters

Any piece of data in a Vala application is considered an instance of a data type. There are various different categories of data types, some being built into Vala, and others being user defined. Details about types are described elsewhere in this documentation, in particular see [Types](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Types#).

Instances of these types are created in various different ways, depending on the type. For example, fundamental types are instantiated with literal expressions, and classed types with the new operator.

In order to access data, the instance must be identifiable in some way, such as by a name. In Vala, there are broadly three ways that this is done, with similar but not identical semantics.

(All these subsections refer to ownership, so it may be useful to read the section on [Concepts/References and ownership](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#References_and_ownership) in conjunction with this section)
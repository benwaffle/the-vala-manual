# Variables, fields and parameters

Any piece of data in a Vala application is considered an instance of a data type. There are different categories of data types, some being built into Vala, and others being user defined. Details about types are described elsewhere in this documentation - see [Types](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Types#).

Instances of these types are created in different ways, depending on the type. For example, fundamental types are instantiated with literal expressions. Classed types use the new operator.

In order to access data, the instance must be identifiable in some way, such as by a name. In Vala, there are broadly three ways that this is done, with similar but not identical semantics.

(All these subsections refer to ownership, so it may be useful to read the section on [Concepts/References and ownership](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#References_and_ownership) in conjunction with this section)

#### Variables

Within executable code in a method, an instance may be assigned to a variable. A variable has a name and is declared to refer to an instance of a particular data type. A typical variable declaration would be:

    int a;

This declaration defines that "a" should become an expression that evaluates to an instance of the int type. The actual value of this expression will depend on which int instance is assigned to the variable. "a" can be assigned to more than once, with the most recent assignment being the only one considered when "a" is evaluated. Assignment to the variable is achieved via an assignment expression. Generally, the semantics of an assignment expression depends on the type of the variable.

A variable can take ownership of an instance, the precise meaning of which depends on the data type. In the context of reference types, it is possible to declare that a variable should not ever take ownership of an instance. This is done with the `unowned` keyword. See [Types/Reference types](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Types#Reference_types).

If a type is directly instantiated in a variable declaration statement, then the variable will be created owning that new instance. For example:

    string s = "stringvalue";

A variable ceases to exist when its scope is destroyed, that is when the code block it is defined in finishes. After this, the name can no longer be used to access the instance, and no new assignment to the variable is allowed. What happens to the instance itself is dependent on the type.

For more details of the concepts in this section, see [Statements/Variable declaration](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Statements#Variable_declaration) and [Expressions/Assignment operations](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Expressions#Assignment_operations).

#### Fields

A field is similar to a variable, except for the scope that it is defined in. Fields can be defined in namespaces, classes and structs. In the case of classes and structs, they may be either in the scope of the the class or struct, or in the scope of each instance of the class or struct.

A field is valid as long as its scope still exists. For non-instance fields, this is the entire life of the application. For instance fields, this is the lifetime of the instance.

Like variables, fields can take ownership of instances, and it is again possible to avoid this with the `unowned` keyword.

If a type is directly instantiated in the declaration of the field, then that field will be created owning that new instance.

For more details about fields, see [Namespaces](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Namespaces#), [Classes](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#) and [Structs](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Structs#).

#### Parameters

Instances passed to methods are accessible within that method with names given in the method's parameter list.

They act like variables, except that they cannot, by default, take ownership of the first instance that is assigned to them, i.e. the instance passed to the method. This behaviour can be changed using explicit ownership transfer. When reassigning to a parameter, the result depends on the parameter direction. Assuming the parameter has no direction modifier, it will subsequently act exactly as a variable.

For more details of methods and parameters, see [Methods](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Methods#) and [Expressions/Ownership transfer expressions](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Expressions#Ownership_transfer_expressions).
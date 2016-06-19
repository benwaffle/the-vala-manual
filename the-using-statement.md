<div id="the-using-statement" class="section level1">

The "using" statement
=====================

`using` statements can be used to avoid having to qualify names fully on
a file-by-file basis. For all identifiers in the same file as the using
statement, Vala will first try to resolve them following the usual rules
(see [Concepts/Scope and
naming](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#Scope_and_naming)
). If the identifier cannot be resolved in any scope, each namespace
that is referenced in a `using` will be searched in turn.

-   using-statement:

    -   **using** namespace-list **;**

    namespace-list:

    -   qualified-namespace-name [ **,** namespace-list ]

There can be any number of using statements in a Vala source file, but
they must all appear outside any other declarations. Note that `using`
is not like import statements in other languages - it does not load
anything, it just allows for automatic searching of namespace scopes, in
order to allow frugal code to be written.

Most code depends on members of the GLib namespace, and so many source
files begin with:

    using GLib;

TODO: Include examples.

Back to [Vala Reference
Manual](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual#)

<div id="methods" class="section level2">

Methods
-------

TODO: Do we really need this discussion? Are we introducing Vala, or
general programming?

A method is an executable statement block that can be identified in one
or more ways (i.e. by a name, or any number of delegate instances). A
method can be invoked with an optional number of parameters, and may
return a value. When invoked, the method's body will be executed with
the parameters set to the values given by the invoker. The body is run
in sequence until the end is reached, or a return statement is
encountered, resulting in a return of control (and possibly some value,
in the case of a return) to the invoker.

There are various contexts that may contain method declarations (see
[Namespaces](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Namespaces#)
,
[Classes](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#)
,
[Interfaces](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Interfaces#)
,
[Structs](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Structs#)
). A method is always declared inside one of these other declarations,
and that declaration will mark the parent scope that the method will be
executed within. See [Concepts/Scope and
naming](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#Scope_and_naming)
.

The
[Classes](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#)
section of this documentation talks about both methods and abstract
methods. It should be noted that the latter are not truly methods, as
they cannot be invoked. Instead, they provide a mechanism for declaring
how other methods should be defined. See
[Classes](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#)
for a description of abstract methods and how they are used.

The syntax for invoking a method is described on the expressions page
(see [Expressions/Invocation
expressions](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Expressions#Invocation_expressions)
).

</div>

</div>

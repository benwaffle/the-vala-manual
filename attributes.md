Attributes
----------

Attributes are metadata information that applies to a symbol (a class, field, parameter, etc.). This extra information is used to:

-   Integrate libraries more directly. These are the ones most often used in new Vala programs/libraries.

-   Control C code generation, particularly with existing libraries. Mostly used in bindings.

-   Give extra information to Vala that isn't included in code. Mostly used internally in Vala.

Most of these attributes are only useful within bindings. Some, however, are useful in normal code:

-   `[DBus]` , `[Description]` , `[Deprecated]` , `[Signal]` , `[ModuleInit]` (if you're writing a module).

-   `CCode` 's `instance_pos` (if you're using `Gtk.Builder` 's signal auto-connection functionality).



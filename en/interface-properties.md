

Interface properties
====================

Interfaces can contain properties in a similar way to classes. As interfaces can not contain per instance data, interface properties cannot be created automatically. This means that all properties must either be declared abstract (and implemented by implementing classes,)
or have explicit get and set clauses as appropriate. Vala does not allow an abstract property to be partially implemented, instead it should just define which actions (get, set or both) should be implemented.

Interfaces are not constructed, and so there is not concept of a construction property in an interface. For more on properties in classes, see: [Classes/Properties](properties.md).

-   interface-instance-property-declaration:

    -   [ class-member-visibility-modifier ] [ class-method-type-modifier ] qualified-type-name property-name **{** accessors [ default-value ] **}** **;**

    -   [ class-member-visibility-modifier ] **abstract** qualified-type-name property-name **{** automatic-accessors **}** **;**


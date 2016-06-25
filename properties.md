Properties
==========

Properties are an enhanced version of fields. They allow custom code to be called whenever the property is retrieved or assigned to, but may be treated as fields by external Vala code. Properties also function like methods to some extent, and so can be defined as virtual and overridden in subclasses. Since they are also allowed in interfaces, they allow interfaces to declare data members that implementing classes must expose (see [Interfaces](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Interfaces#).)

> **Notes**
> 
> Class and static properties are not yet supported.
> 
> Fully managed properties are only available to GObject derived classes - these are properties that can be set dynamically (by providing the property name at runtime) and can have attached metadata, as is often used in the GTK+ and GNOME libraries. The other class types can have unmanaged properties, which appear similar when using Vala, but are actually implemented using simple methods.

Declaration
-----------

-   class-instance-property-declaration:

    -   [ class-member-visibility-modifier ] [ class-method-type-modifier ] qualified-type-name property-name **{** accessors [ default-value ] **}** **;**


-   class-instance-abstract-property-declaration:

    -   [ class-member-visibility-modifier ] **abstract** qualified-type-name property-name **{** automatic-accessors **}** **;**


-   class-class-property-declaration:

    -   [ class-member-visibility-modifier ] **class** qualified-type-name property-name **{** accessors [ default-value ] **}** **;**

-   class-static-property-declaration:

    -   [ class-member-visibility-modifier ] **static** qualified-type-name property-name **{** accessors [ default-value ] **}** **;**

-   property-name:

    -   identifier

-   accessors:

    -   automatic-accessors

        [ getter ] [ setter ] [ property-constructor ]

-   automatic-accessors:

    -   [ automatic-getter ] [ automatic-setter ] [automatic-property-constructor ]

-   automatic-getter:

    -   [ class-member-visibility-modifier ] **get** **;**

-   automatic-setter:

    -   [ class-member-visibility-modifier ] **set** [ **construct** ] **;**

-   automatic-property-constructor:

    -   [ class-member-visibility-modifier ] **construct** **;**

-   get-accessor:

    -   [ class-member-visibility-modifier ] **get** **{** statement-list **}**

-   set-accessor:

    -   [ class-member-visibility-modifier ] **set** [ **construct** ] **{** statement-list **}**

-   property-constructor:

    -   [ class-member-visibility-modifier ] **construct** **{** statement-list **}**

-   default-value:

    -   **default** **=** expression **;**


Execute Code on Setting/Getting Values
--------------------------------------

Properties can either be declared with code that will perform particular actions on get and set, or can simply declare which actions are allowed and allow Vala to implement simple get and set methods. This second pattern (automatic property) will result in fields being added to the class to store values that the property will get and set. If either get or set has custom code, then the other must either be also written in full, or omitted altogether.

When a value is assigned to a property, the **set** block is invoked, with a parameter called **value** of the same type as the property. When a value is requested from a property, the **get** block is invoked, and must return an instance of the same type of the property.

Construct / Set Construct Block
-------------------------------
A property may have zero or one **construct** blocks. This means either a **set construct** block or a separate **construct** block. If this is the case that then the property becomes a construct property, meaning that if it is set in creation method, it will be set (using the construct block, as opposed to any simple **set** block, where there is a distinction) before class construct blocks are called.

Notify Changes Signals
----------------------
Managed properties may be annotated with Notify, See [Attributes](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Attributes#). This will cause the class instance to emit a notify signal when the property has been assigned to.

Virtual Properties
------------------
Instance properties can be defined virtual with the same semantics as for virtual methods. If in an abstract class, an instance property can be defined as abstract. This is done using the "abstract" keyword on a declaration that is otherwise the same as an automatic property. It is then the responsibility of derived classes to implement the property by providing get or set blocks as appropriate. An abstract property is automatically virtual.

Abstract Properties
-------------------
As with methods, it is possible to declare abstract properties. These have much the same semantics as abstract methods, i.e. all non-abstract subclasses will have to implement properties with at least the accessors defined in the abstract property. Any **set construct** or construct accessor must be defined too in non-abstract classes and use **override**.

-   class-instance-abstract-property-declaration:

    -   [ class-member-visibility-modifier ] **abstract** qualified-type-name property-name **{** automatic-accessors **}** **;**


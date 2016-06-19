<div id="class-methods" class="section level1">

Class methods
=============

Class methods are methods bound to a particularly class or class
instance, i.e. they are executed within the scope of that class or class
instance. They are declared the same way as other methods, but within
the declaration of a class.

The same visibility modifiers can be used as for fields, although in
this case they refer to what code can call the methods, rather than who
can see or change values.

The `static` modifier is applicable to methods also. A static method is
independent of any instance of the class. It is therefore only in the
class scope, and may only access other `static` members.

-   class-instance-method-declaration:

    -   [ class-member-visibility-modifier ] [
        class-method-type-modifier ] return-type method-name **(** [
        params-list ] **)** method-contracts [ **throws**
        exception-list] **{** statement-list **}**

    class-class-method-declaration:

    -   [ class-member-visibility-modifier ] **class** return-type
        method-name **(** [ params-list ] **)** method-contracts [
        **throws** exception-list ] **{** statement-list **}**

    class-static-method-declaration:

    -   [ class-member-visibility-modifier ] **static** return-type
        method-name **(** [ params-list ] **)** method-contracts [
        **throws** exception-list ] **{** statement-list **}**

    class-method-type-modifier:

    -   **virtual**

        **override**

Methods can be virtual, as described in [Concepts/Object oriented
programming](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#Object_oriented_programming)
. Methods in Vala classes are not virtual automatically, instead the
"virtual" modifier must be used when it is needed. Virtual methods will
only chain up if overridden using the override keyword.

Vala classes may also define abstract methods, by writing the
declaration with the "abstract" modifier and replacing the method body
with an empty statement ";". Abstract methods are not true methods, as
they do not have an associated statement block, and so cannot be
invoked. Abstract methods can only exist in abstract classes, and must
be overridden in derived classes. For this reason an abstract method is
always virtual. The purpose of an abstract method is to define methods
that all non-abstract subclasses of the current definition must
implement, it is therefore always allowable to invoke the method on an
instance of the abstract class, because it is required that that
instance must in fact be of a non-abstract subclass.

-   class-instance-abstract-method-declaration:

    -   [ class-member-visibility-modifier ] **abstract** return-type
        method-name **(** [ params-list ] **)** method-contracts [
        **throws** exception-list ] **;**

> **Note**
>
> -   **Note**
>
>     *Virtual methods are not available to compact classes.*
>
> Properties
> ==========

> **Note**
>
> -   **Development Note:**
>
>     *Class and static properties are not yet supported in current Vala
>     releases.*
>
> **Note**
>
> -   **Note**
>
>     *Fully managed properties are only available to GObject derived
>     classes - these are properties that can be set dynamically (by
>     providing the property name at runtime) and can have attached
>     metadata, as is often used in the GTK+ and GNOME libraries. The
>     other class types can have unmanaged properties, which appear
>     similar when using Vala, but are actually implemented using simple
>     methods.*
>
> Properties are an enhanced version of fields. They allow custom code
> to be called whenever the property is retrieved or assigned to, but
> may be treated as fields by external Vala code. Properties also
> function like methods to some extent, and so can be defined as virtual
> and overridden in subclasses. Since they are also allowed in
> interfaces, they allow interfaces to declare data members that
> implementing classes must expose (see
> [Interfaces](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Interfaces#)
> .)

<div id="declaration" class="section level2">

Declaration
-----------

-   class-instance-property-declaration:

    -   [ class-member-visibility-modifier ] [
        class-method-type-modifier ] qualified-type-name property-name
        **{** accessors [ default-value ] **}** **;**

    class-instance-abstract-property-declaration:

    -   [ class-member-visibility-modifier ] **abstract**
        qualified-type-name property-name **{** automatic-accessors
        **}** **;**

    class-class-property-declaration:

    -   [ class-member-visibility-modifier ] **class**
        qualified-type-name property-name **{** accessors [
        default-value ] **}** **;**

    class-static-property-declaration:

    -   [ class-member-visibility-modifier ] **static**
        qualified-type-name property-name **{** accessors [
        default-value ] **}** **;**

    property-name:

    -   identifier

    accessors:

    -   automatic-accessors

        [ getter ] [ setter ] [ property-constructor ]

    automatic-accessors:

    -   [ automatic-getter ] [ automatic-setter ] [
        automatic-property-constructor ]

    automatic-getter:

    -   [ class-member-visibility-modifier ] **get** **;**

    automatic-setter:

    -   [ class-member-visibility-modifier ] **set** [ **construct** ]
        **;**

    automatic-property-constructor:

    -   [ class-member-visibility-modifier ] **construct** **;**

    get-accessor:

    -   [ class-member-visibility-modifier ] **get** **{**
        statement-list **}**

    set-accessor:

    -   [ class-member-visibility-modifier ] **set** [ **construct** ]
        **{** statement-list **}**

    property-constructor:

    -   [ class-member-visibility-modifier ] **construct** **{**
        statement-list **}**

    default-value:

    -   **default** **=** expression **;**

</div>

<div id="execute-code-on-settinggetting-values" class="section level2">

Execute Code on Setting/Getting Values
--------------------------------------

Properties can either be declared with code that will perform particular
actions on get and set, or can simply declare which actions are allowed
and allow Vala to implement simple get and set methods. This second
pattern (automatic property) will result in fields being added to the
class to store values that the property will get and set. If either get
or set has custom code, then the other must either be also written in
full, or omitted altogether.

When a value is assigned to a property, the **set** block is invoked,
with a parameter called **value** of the same type as the property. When
a value is requested from a property, the **get** block is invoked, and
must return an instance of the same type of the property.

</div>

<div id="construct-set-construct-block" class="section level2">

Construct / Set Construct Block
-------------------------------

A property may have zero or one **construct** blocks. This means either
a **set construct** block or a separate **construct** block. If this is
the case that then the property becomes a construct property, meaning
that if it is set in creation method, it will be set (using the
construct block, as opposed to any simple **set** block, where there is
a distinction) before class construct blocks are called.

</div>

<div id="notify-changes-signals" class="section level2">

Notify Changes Signals
----------------------

Managed properties may be annotated with Notify, See
[Attributes](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Attributes#)
. This will cause the class instance to emit a notify signal when the
property has been assigned to.

</div>

<div id="virtual-properties" class="section level2">

Virtual Properties
------------------

Instance properties can be defined virtual with the same semantics as
for virtual methods. If in an abstract class, an instance property can
be defined as abstract. This is done using the "abstract" keyword on a
declaration that is otherwise the same as an automatic property. It is
then the responsibility of derived classes to implement the property by
providing get or set blocks as appropriate. An abstract property is
automatically virtual.

</div>

<div id="abstract-properties" class="section level2">

Abstract Properties
-------------------

As with methods, it is possible to declare abstract properties. These
have much the same semantics as abstract methods, i.e. all non-abstract
subclasses will have to implement properties with at least the accessors
defined in the abstract property. Any **set construct** or construct
accessor must be defined too in non-abstract classes and use
**override** .

-   class-instance-abstract-property-declaration:

    -   [ class-member-visibility-modifier ] **abstract**
        qualified-type-name property-name **{** automatic-accessors
        **}** **;**

</div>

</div>

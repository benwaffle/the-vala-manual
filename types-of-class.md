<div id="types-of-class" class="section level1">

Types of class
==============

Vala supports three different types of class:

-   GObject subclasses are any classes derived directly or indirectly
    from GLib.Object. This is the most powerful type of class,
    supporting all features described in this page. This means signals,
    managed properties, interfaces and complex construction methods,
    plus all features of the simpler class types.

-   Fundamental GType classes are those either without any superclass or
    that don't inherit at any level from GLib.Object. These classes
    support inheritence, interfaces, virtual methods, reference
    counting, unmanaged properties, and private fields. They are
    instantiated faster than GObject subclasses but are less powerful -
    it isn't recommended in general to use this form of class unless
    there is a specific reason to.

-   Compact classes, so called because they use less memory per
    instance, are the least featured of all class types. They are not
    registered with the GType system and do not support reference
    counting, virtual methods, or private fields. They do support
    unmanaged properties. Such classes are very fast to instantiate but
    not massively useful except when dealing with existing libraries.
    They are declared using the Compact attribute on the class, See

Any non-compact class can also be defined as abstract. An abstract class
cannot be instantiated and is used as a base class for derived classes.

</div>

<div id="gtype-and-gobject" class="section level1">

GType and GObject
=================

Vala uses the runtime type system called GType. This system allows every
type in Vala, including the fundamental types, to be identified at
runtime. A Vala developer doesn't need to be aware of GType in most
circumstances, as all interaction with the system is automatic.

GType provides Vala with a powerful object model called GObject. To all
types descended from GLib.Object class, this model provides for features
such as properties and signals.

GType and GObject are entirely runtime type systems, intended to be
usable to dynamically typed languages. Vala is primarily a statically
typed language, and so is designed not to provide access to all of GType
and GObject's features. Instead Vala uses a coherent subset to support
particular programming styles.

Vala is designed to use GType and GObject seamlessly. There are
occasions, mostly when working with existing libraries, when you might
need to circumvent parts of the system. These are all indicated in this
documentation.

</div>

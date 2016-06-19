<div id="memory-management" class="section level1">

Memory management
=================

Vala automatically uses the memory management system in GLib, which is a
reference counting system. In order for this to work, the types used
must support reference counting, as is the case with all GObject derived
types and some others.

Memory is allocated and initialised by Vala when needed. The memory
management scheme means it is also freed when possible. There is though
no garbage collector, and currently reference cycles are not
automatically broken. This can lead to memory being leaked. The main way
to avoid this problem is to use weak references - these are not counted
references and so cannot prevent memory being released, at the cost that
they can be left refering to non existent data.

Vala also allows use of pointers in much the same way as C. An instance
of a pointer type refers directly to an address in memory. Pointers are
not references, and therefore the automatic memory management rules do
not apply in the same way. See [Types/Pointer
types](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Types#Pointer_types).

There are more details about memory management elsewhere, see
[Types](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Types#),
see
[Concepts](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#)
.

</div>
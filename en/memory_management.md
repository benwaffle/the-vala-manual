# Memory Management
Vala automatically uses the reference counting memory management system in GLib. In order for this to work, the types used must support reference counting. This is the case with all GObject derived types.

Memory is allocated and initialised by Vala when needed. The memory management scheme means it is also freed when possible. There is no garbage collector.

Vala also allows use of pointers in much the same way as C. An instance of a pointer type refers directly to an address in memory. Pointers are not references, and the automatic memory management rules do not apply in the same way. See [Types/Pointer types](pointer_types.md).

There are more details about memory management in the [References and Ownership](references_and_owndership.md) section.
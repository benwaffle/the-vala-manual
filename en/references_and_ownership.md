# References and ownership

Type instances in Vala are automatically managed to a large degree. This means that memory is allocated to store the data, and then deallocated when it is no longer required. Vala does not have a runtime garbage collector, instead it applies rules at compile time that will predictably deallocate memory at runtime.

A central concept of Vala's memory management system is ownership. An instance is considered still in use as long as there is at least one way of accessing it, i.e. there is some field, variable or parameter that refers to the instance. One such identifier will be considered the instance's owner, and therefore the instance's memory will not be deallocated. When there is no longer any way to access the data instance, it is considered unowned, and its memory will be deallocated.

#### Value types

When dealing with instances of value types (see [Types](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Types#)) knowledge of ownership is rarely important. This is because the instance is copied whenever it is assigned to a new identifier. This will cause each identifier to become owner of a unique instance - that instance will then be deallocated when the identifier ceases to be valid.

There is one exception to this rule: when a struct type instance is passed to a method, Vala will, by default, create the method parameter as a reference to the instance instead of copying the instance. This reference is a weak reference, as described in the following section. If the struct should instead be copied, and the parameter created as a standard value type identifier, the ownership transfer operator should be used (see [Expressions/Ownership transfer expressions](ownership-transfer-expressions.md)).

#### Reference types

With reference types, it is possible for several identifiers to reference the same data instance. Not all identifiers that refer to reference type instance are capable of owning the instance, for reasons that will be explained. It is therefore often required to think about instance ownership when writing Vala code.

Most reference types support reference counting. This means that the instance internally maintains a count of how many references to it currently exist. This count is used to decide whether the instance is still in use, or if its memory can be deallocated. Each reference that is counted in this way is therefore a potential owner of the instance, as it ensures the instance continues to exist. There are situations when this is not desired, and so it is possible to define a field or variable as "weak". In this case the reference is not counted, and so the fact that the reference exists will not stop the instance being possibly deallocated, i.e. this sort of reference cannot take ownership of the instance.

When using reference counted types, the main use for weak references is to prevent reference cycles. These exist when a data instance contains internally a reference to another instance, which in turn contains a reference to the first. In this case it would not be possible to deallocate the instances, as each would be potentially owning the other. By ensuring that one of the references is weak, one of the instances can become unowned and be deallocated, and in the process the other will be dereferenced, and potentially become unowned and be deallocated also.

It is also possible to have reference types which are not reference counted; an example of this is the fundamental string type, others are compact classed types. If Vala were to allow several references to own such instances, it would not be able to keep track of when they all ceased to exist, and therefore would not be able to know when to deallocate the instance. Instead, exactly one or zero identifiers will own the instance - when it is zero, the instance is deallocated. This means that all references to an already owned instance must either be weak references, or ownership must be specifically passed to the new reference, using the ownership transfer operator (see [Expressions/Ownership transfer expressions](ownership-transfer-expressions.md)).

#### Pointer types

Pointer types are of great importance. Pointer types are value types, whose instances are references to some other data instance. They are therefore not actual references, and will never own the instance that they indirectly refer to. See [Types/Pointer types](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Types#Pointer_types).
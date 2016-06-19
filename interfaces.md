# Interfaces

An interface in Vala is a non-instantiable type. A class may implement any number of interfaces, thereby declaring that an instance of that class should also be considered an instance of those interfaces. Interfaces are part of the GType system, and so compact classes may not implement interfaces (see [Classes/Types of class](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#Types_of_class).)

The simplest interface declaration looks like this:

```vala
	interface InterfaceName {
	
	}
```

Unlike C\# or Java, Vala's interfaces may include implemented methods, and so provide premade functionality to an implementing class, similar to mixins in other languages. All methods defined in a Vala interface are automatically considered to be virtual. Interfaces in Vala may also have prerequisites - classes or other interfaces that implementing classes must inherit from or implement. This is a more general form of the interface inheritence found in other languages. It should be noted that if you want to guarantee that all implementors of an interface are GObject type classes, you should give that class as a prerequisite for the interface.

Interfaces in Vala have a static scope, identified by the name of the interface. This is the only scope associated with them (i.e. there is no class or instance scope created for them at any time.) Non-instance members of the interface (static members and other declarations,) can be identified using this scope.

For an overview of object oriented programming, see [Concepts/Object oriented programming](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#Object_oriented_programming).

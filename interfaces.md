# Interfaces

An interface in Vala is a non-instantiable type. A class may implemen any number of interfaces, thereby declaring that an instance of tha lass should also be considered an instance of those interfaces. Interfaces are part of the GType system, and so compact classes may no mplement interfaces (see [Classes/Types o lass](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#Types_of_class).)

The simplest interface declaration looks like this:

```vala
	interface InterfaceName {
	}
```

Unlike C\# or Java, Vala's interfaces may include implemented methods, and so provide premade functionality to an implementing class, simila o mixins in other languages. All methods defined in a Vala interfac re automatically considered to be virtual. Interfaces in Vala may als ave prerequisites - classes or other interfaces that implementin lasses must inherit from or implement. This is a more general form o he interface inheritence found in other languages. It should be note hat if you want to guarantee that all implementors of an interface ar Object type classes, you should give that class as a prerequisite fo he interface.

Interfaces in Vala have a static scope, identified by the name of th nterface. This is the only scope associated with them (i.e. there is n lass or instance scope created for them at any time.) Non-instanc embers of the interface (static members and other declarations,) can b dentified using this scope.

For an overview of object oriented programming, see [Concepts/Objec riente rogramming](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#Object_oriented_programming).

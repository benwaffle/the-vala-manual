Classes
-------

A class is definition of a data type. A class can contain fields,
constants, methods, properties, and signals. Class types support inheritance, a mechanism whereby a derived class can extend and specialize a base class.

The simplest class declaration looks like this:

```vala
class ClassName { }
```

As class types support inheritance, you can specify a base class you want to derive from. A derived class is-a superclass. It gets access to some of its methods etc. It can always be used in place of a and so on....

No classes can have multiple base classes, however GObject subclasses may implement multiple interfaces. By implementing an interface, a classed type has an is-a relationship with an interface. Whenever an instance of that interface is expected, an instance of this class will do.



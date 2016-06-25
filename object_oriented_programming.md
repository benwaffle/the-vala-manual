# Object oriented programming

Vala is primarily an object oriented language. This documentation isn't going to describe object oriented programming in detail, but in order for other sections to make sense, some things need to be explained.

A class in Vala is a definition of a potentially polymorphic type. A polymorphic type is one which can be viewed as more than one type. The basic method for this is inheritance, whereby one type can be defined as a specialized version of another. An instance of a subtype, descended from a particular supertype, has all the properties of the supertype. It can be used wherever an instance of the supertype is expected. This sort of relationship is described as a "subtype instance is-a supertype instance." See [Classes](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#).

Vala provides inheritance functionality to any type of class (see [Classes/Types of class](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#Types_of_class) ). Given the following definition, every SubType instance is-a SuperType instance:

```vala
class SuperType {
	public int act () {
		return  1;
	}
}

class SubType : SuperType {

}  
```
Whenever a SuperType instance is required, a SubType instance may be used. This is the extent of inheritence allowed to compact classes, but full classes are more featured. All classes that are not of compact type, can have virtual methods, and can implement interfaces.

To explain virtual functions, it makes sense to look at the alternative first. In the above example, it is legal for SubType to also define a method called "act" - this is called overriding. In this case, when a method called "act" is called on a SubType instance, which method is invoked depends on what type the invoker believed it was dealing with. The following example demonstrates this:

```vala
SubType sub = new SubType();
SuperType super = sub;
sub.act();
super.act(); 
```

Here, when sub.act() is called, the method invoked will be SubType's "act" method. The call super.act() will call SuperType's "act". If the act method were virtual, the SubType.act method would have been called on both occasions. See [Classes/Class methods](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#Class_methods) for how to declare virtual methods.

Interfaces are a variety of non-instantiatable type. This means that it is not possible to create an instance of the type. Instead, interfaces are implemented by other types. Instances of these other types may then be used as though they were instances of the interface in question. See [Interfaces](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Interfaces#).
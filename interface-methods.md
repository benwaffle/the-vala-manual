<div id="interface-methods" class="section level1">

Interface methods
=================

Interfaces can contain abstract and non abstract methods. A non-abstract
class that implements the interface must provide implementations of all
abstract methods in the interface. All methods defined in an interface
are automatically virtual.

Vala interfaces may also define static methods. These are equivalent to
static methods in classes.

-   interface-instance-method-declaration:

    -   [ class-member-visibility-modifier ] return-type method-name
        **(** [ params-list ] **)** method-contracts [ **throws**
        exception-list ] **{** statement-list **}**

    interface-instance-abstract-method-declaration:

    -   [ class-member-visibility-modifier ] **abstract** return-type
        method-name **(** [ params-list ] **)** method-contracts [
        **throws** exception-list ] **;**

    interface-static-method-declaration:

    -   [ class-member-visibility-modifier ] **static** return-type
        method-name **(** [ params-list ] **)** method-contracts [
        **throws** exception-list ] **{** statement-list **}**

For discussion of methods in classes, see: [Classes/Class
methods](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Classes#Class_methods)
. For information about methods in general, see
[Methods](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Methods#)
. Of particular note is that an abstract method of an interface defines
a method that can always be called in an instance of an interface,
because that instance is guaranteed to be of a non-abstract class that
implements the interface's abstract methods.

</div>

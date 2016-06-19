

Controlling instantiation
=========================

When a class is instantiated, data might be required from the user to set initial properties. To define which properties should be or can be set at this stage, the class declaration should be written as:

``` {.vala}
          class
           
          ClassName
           : 
          GLib
          .
          Object
           {
                  
          public
           
          ClassName
          () {
                  }
                  
          public
           
          ClassName
          .
          with_some_quality
           (
          Property1Type
           
          property1value
          ) {
                 
          this
          .
          property1
           = 
          property1value
          ;
                  }
          }
        
```

This example allows the
[ClassName](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/ClassName#)
class to be instantiated either setting no properties, or setting the property. The convention is to name constructors as "with\_" and then a description of what the extra properties will be used for, though following this is optional.

-   class-creation-method-declaration:

    -   [ class-member-visibility-modifier ] class-name [ **.**
        creation-method-name ] **(** param-list **)** **{**
        construction-assignments **}**

    class-name:

    -   identifier

    creation-method-name:

    -   identifier

    construction-assignments:

    -   this **.** property-name **=** param-name **;**

class-name must be the same as the name of the class. If a creation method is given an extra name, this name is also used with instantiating the class, using the same syntax as for declaring the method, e.g.
`var a = new Button.with_label ("text")` .

If the property being set is construct type then assignment is made before construction, else afterwards.

Any number of these are allowed, but only one with each name (including null name.)

> **Note**
>
> -   **Note:**
>
>     *For a GObject derived class, only properties may be set at this
>     stage in construction, no other processing can be done at this
>     time.*
>
> Construction
> ============

> **Note**
>
> -   **Note:**
>
>     *Construction only follows this process in GObject derived
>     classes.*
>
> During instantiaion, after construction properties have been set, a
> series of blocks of code are executed. This is the process that
> prepares the instance for use. There are three types of `construct`
> blocks that a class may define:

-   class-instance-constructor-declaration:

    -   **construct** **{** statement-list **}**

Code in this block is executed on every instance of the class that is instantiated. It is run after construction properties have been set.

-   class-class-constructor-declaration:

    -   **class** **construct** **{** statement-list **}**

This block will be executed once at the first use of its class, and once at the first use of each subclass of this class.

-   class-static-constructor-declaration:

    -   **static** **construct** **{** statement-list **}**

The first time that a class, or any subclass of it, is instantiated,
this code is run. It is guaranteed that this code will run exactly once in a program where such a class is used.

The order of execution for constructors:

-   class-instance-destructor-declaration:

    -   **\~** class-name **(** **)** **{** statement-list **}**

Destruction here. When does it happen? And when for each type of class?


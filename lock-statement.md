<div id="lock-statement" class="section level1">

Lock statement
==============

Locks Statements are the main part of Vala's resource control mechanism.

FIXME: Haven't actually written anything here about resource control.

-   lock-statement:

    -   **lock** **(** identifier **)** embedded-statement

Back to [Vala Reference
Manual](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual#)

<div id="namespaces" class="section level2">

Namespaces
----------

Namespaces are named scopes (see [Concepts/Scope and
naming](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Concepts#Scope_and_naming)
). Definitions in different namespaces can use the same names without
causing conflicts. A namespace can be declared across any number of Vala
source files, and there can be multiple namespaces defined in a single
Vala source file. Namespaces can be nested to any depth.

When code needs to access definitions from other namespaces, it must
either refer to them using a fully qualified name, or be written in a
file with an appropriate using statement.

The simplest namespace declaration looks like this:

``` {.vala}
        namespace
         
        NameSpaceName
         {
        }
      
```

Namespace nesting is achieved either by nesting the declarations, or by
providing multiple names in one declaration:

``` {.vala}
        namespace
         
        NameSpaceName1
         {
                
        namespace
         
        NameSpaceName2
         {
                }
        }
        namespace
         
        NameSpaceName1
        .
        NameSpaceName2
         {
        }
      
```

</div>

</div>

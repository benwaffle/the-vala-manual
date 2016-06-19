<div id="class-scope" class="section level1">

Class scope
===========

Class scope is more complicated than other scopes, but conceptually the
same. A class has a scope, which consists of its static and class
members, as describe above. When an instance of the class is created, it
is given its own scope, consisting of the defined instance members, with
the class' scope as its parent scope.

Within the code of a class, the instance and class scopes are
automatically searched as appropriate after the local scope, so no
qualification is normally required. When there is a conflict with a name
in the local scope, the `this` scope can be used, for example:

``` {.vala}
          class
           
          ClassName
           {
                  
          int
           
          field_name
          ;
                  
          void
           
          function_name
          (
          field_name
          ) {
                 
          this
          .
          field_name
           = 
          field_name
          ;
                  }
          }
        
```

When a name is defined in a class which conflicts with one in a
subclass, the `base` scope can be used, to refer to the scope of the
subclass.

</div>

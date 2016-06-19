<div id="examples-5" class="section level1">

Examples
========

Demonstrating...

``` {.vala}
          using
           
          GLib
          ;
          public
           
          interface
           
          With
           < 
          T
           > {
                  
          public
           
          abstract
           
          void
           
          sett
          (
          T
           
          t
          );
                  
          public
           
          abstract
           
          T
           
          gett
          ();
          }
          public
           
          class
           
          One
           : 
          Object
          , 
          With
           < 
          int
           > {
                  
          public
           
          int
           
          t
          ;
                  
                  
          public
           
          void
           
          sett
          (
          int
           
          t
          ) {
                 
          this
          .
          t
           = 
          t
          ;
                  }
                  
          public
           
          int
           
          gett
          () {
                 
          return
           
          t
          ;
                  }
          }
          public
           
          class
           
          Two
           < 
          T
          , 
          U
           > : 
          Object
          , 
          With
           < 
          T
           > {
                  
          public
           
          T
           
          t
          ;
                  
                  
          public
           
          void
           
          sett
          (
          T
           
          t
          ) {
                 
          this
          .
          t
           = 
          t
          ;
                  }
                  
          public
           
          T
           
          gett
          () {
                 
          return
           
          t
          ;
                  }
                  
                  
          public
           
          U
           
          u
          ;
          }
          public
           
          class
           
          Test
           : 
          GLib
          .
          Object
           {
                  
                  
          public
           
          static
           
          void
           
          main
          (
          string
          [] 
          args
          ) {
                 
          var
           
          o
           = 
          new
           
          One
           ();
                 
          o
          .
          sett
          (5);
                 
          stdout
          .
          printf
          (
          "
          %d
          
          
          "
          , 
          o
          .
          t
          );
                 
                 
          var
           
          t
           = 
          new
           
          Two
           < 
          int
          , 
          double
           > ();
                 
          t
          .
          sett
          (5);
                 
          stdout
          .
          printf
          (
          "
          %d
          
          
          "
          , 
          t
          .
          t
          );
                 
                 
          t
          .
          u
           = 5.0f;
                 
          stdout
          .
          printf
          (
          "
          %f
          
          
          "
          , 
          t
          .
          u
          );
                  }
          }
        
```

Back to [Vala Reference
Manual](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual#)

<div id="structs" class="section level2">

Structs
-------

A struct is a data type that can contain fields, constants, and methods.

The simplest struct declaration looks like this:

``` {.vala}
        struct
         
        StructName
         {
            
        int
         
        some_field
        ;
        }
      
```

A struct must have at least one field, except in either one of the
following cases:

-   It's external

-   It has either one of `[BooleanType]` , `[IntegerType]` or
    `[FloatingType]` attributes

-   It inherits from another struct

</div>

</div>

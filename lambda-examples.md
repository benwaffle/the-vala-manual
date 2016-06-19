Examples
========

Defining delegates:

``` {.vala}
          // Static delegate taking two ints, returning void:
          
          static
           
          void
           
          DelegateName
           (
          int
           
          a
          , 
          int
           
          b
          );
          // Instance delegate with the same signature:
          
          void
           
          DelegateName
           (
          int
           
          a
          , 
          int
           
          b
          );
          // Static delegate which may throw an error:
          
          static
           
          void
           
          DelegateName
           () 
          throws
           
          GLib
          .
          Error
          ;
        
```

Invoking delegates, and passing as parameters.

``` {.vala}
          void
           
          f1
          (
          int
           
          a
          ) { 
          stdout
          .
          printf
          (
          "
          %d
          
          
          "
          , 
          a
          ); }
          ...
          void
           
          f2
          (
          DelegateType
           
          d
          , 
          int
           
          a
          ) {
                  
          d
          (
          a
          );
          }
          ...
          f2
          (
          f1
          , 5);
        
```

Instance delegates:

``` {.vala}
          class
           
          Test
           : 
          Object
           {
                  
          private
           
          int
           
          data
           = 5;
                  
          public
           
          void
           
          method
           (
          int
           
          a
          ) {
                 
          stdout
          .
          printf
          (
          "
          %d %d
          
          
          "
          , 
          a
          , 
          this
          .
          data
          );
                  }
          }
          delegate
           
          void
           
          DelegateType
           (
          int
           
          a
          );
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
           
          t
           = 
          new
           
          Test
          ();
                  
          DelegateType
           
          d
           = 
          t
          .
          method
          ;
                  
                  
          d
          (1);
          }
        
```

With Lambda:

    f2(a => { stdout.printf("%d\n", a); }, 5);

Back to [Vala Referenc anual](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual#)


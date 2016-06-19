

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

Back to [Vala Reference Manual](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual#)



Errors
------

Vala Error handling is just for recoverable runtime errors, anything that can be reasonably foreseen should not be handled with errors, e.g.
passing the wrong args to a method. In that example, a better action is to state that the method's result is undefined on illegal input, and use method contracts or assertions to catch potential problems during development: See [Methods/Contract programming](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Methods#Contract_programming)
. A more suitable use for errors would be reporting missing files, which of course cannot be detected until the program is running.

A method may declare that it throws methods from any number of error domains. Error domains are groups of related errors, each of which is denoted by a unique symbol in much the same way an enumerated type, see
[Enumerated types (Enums)/Error domains](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Enumerated%20types%20%28Enums%29#Error_domains)
for declaration syntax. In Vala it is not allowed to throw arbitrary data as in C++, and there is no class for errors, as in Java.

No error can be thrown must either be caught or declared as being thrown.

When a method declares it may thrown an error, the invoker may choose to either catch the error (should one be thrown), or ignore it, meaning it will be thrown on to that methods caller. In the latter case, the method failing to catch the error must also be declared to throw that type of error. Errors can only be caught when the method throwing it is invoked within the try block of a try statement. A try statement, with its associated catch blocks, can potentially catch all errors thrown in its scope, either with catch blocks for all error domains from which a thrown error might come, or with a generic catch block to catch any error.

When an error is first thrown, the "throw" statement is considered the same as a method which from which an error has been thrown. This means that it is possible to catch errors locally, but this is not good practise. The only proper use of this functionality is to use a finally block to free resources before the error is thrown from the method.

When an error is thrown, the following sequence of events happens:

NB: finally clauses are always run, regardless of if error is thrown and/or handled.


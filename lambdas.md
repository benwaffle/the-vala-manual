<div id="lambdas" class="section level1">

Lambdas
=======

As Vala supports delegates, it is possible to have a method that is
identified by a variable (or field, or parameter.) This section
discusses a Vala syntax for defining inline methods and directly
assigning them to an identifier. This syntax does not add any new
features to Vala, but it is a lot more succinct than the alternative
(defining all methods normally, in order to assign them to variables at
runtime). See
[Delegates](http://wiki.gnome.org/action/show/Projects/Vala/Manual/Export/Vala/Manual/Delegates#)
.

Declaring an inline method must be done with relation to a delegate or
signal, so that the method signature is already defined. Parameter and
return types are then learned from the signature. A lambda definition is
an expression that returns an instance of a particular delegate type,
and so can be assigned to a variable declared for the same type. Each
time that the lambda expression is evaluated it will return a reference
to exactly the same method, even though this is never an issue as
methods are immutable in Vala.

-   lambda-declaration:

    -   **(** [ lambda-params-list ] **)** **=\>** **{** statement-list
        **}**

    lambda-params-list:

    -   identifier [ **,** lambda-params-list ]

An example of lambda use:

``` {.vala}
          delegate
           
          int
           
          DelegateType
           (
          int
           
          a
          , 
          string
           
          b
          );
          int
           
          use_delegate
           (
          DelegateType
           
          d
          , 
          int
           
          a
          , 
          string
           
          b
          ) {
                  
          return
           
          d
           (
          a
          , 
          b
          );
          }
          int
           
          make_delegate
           () {
                  
          DelegateType
           
          d
           = (
          a
          , 
          b
          ) => {
                 
          return
           
          a
          ;
                  };
                  
          use_delegate
          (
          d
          , 5, 
          "
          test
          "
          );
          }
        
```

</div>

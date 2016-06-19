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

A struct must have at least one field, except in either one of the following cases:

-   It's external

-   It has either one of `[BooleanType]` , `[IntegerType]` or `[FloatingType]` attributes

-   It inherits from another struct



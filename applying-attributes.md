

Applying attributes
===================

They are written as:

``` {.vala}
          [ 
          AnnotationName
           ( 
          details
          -
          list
           ) ]
          declaration
        
```

For example:

``` {.vala}
          [ 
          CCode
           ( 
          cname
           = 
          "
          var_c_name
          "
           ) ]
          static
           
          int
           
          my_var
          ;
        
```

